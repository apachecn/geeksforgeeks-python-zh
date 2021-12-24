# 设计 RESTful API 与 SQLite 数据库交互

> 原文:[https://www . geesforgeks . org/design-a-restful-API-to-interaction-SQLite-database/](https://www.geeksforgeeks.org/designing-a-restful-api-to-interact-with-sqlite-database/)

在本章中，我们将为 HTTP 请求创建 Django API 视图，并将讨论 Django 和 Django REST 框架如何处理每个 HTTP 请求。

*   Create Django view
*   Routing URLs to Django views and functions
*   Start Django's development server
*   Use command line tools
*   Use postman to make HTTP request.

## 创建姜戈视图

在前面的章节中，您已经看到了如何创建模型及其序列化程序。现在，让我们看看如何处理 HTTP 请求和提供 HTTP 响应。在这里，我们将创建 Django 视图来处理 HTTP 请求。在接收到一个 HTTP 请求时，Django 创建一个 HTTP request 实例，并将它作为第一个参数传递给视图函数。此实例包含包含 HTTP 谓词(如 GET、POST 或 PUT)的元数据信息。视图函数检查该值，并基于 HTTP 谓词执行代码。这里的代码使用*@ csrf _ exclude*装饰器来设置一个 csrf(跨站点请求伪造)cookie。这使得测试代码变得更加容易，因为代码没有描述一个生产就绪的 web 服务。让我们进入代码实现。

## 蟒 3

```py
from django.http import HttpResponse
from django.views.decorators.csrf import csrf_exempt
from rest_framework.renderers import JSONRenderer
from rest_framework.parsers import JSONParser
from rest_framework import status
from taskmanagement.models import TaskManagement
from taskmanagement.serializers import TaskMngSerializer

class JSONResponse(HttpResponse):
    def __init__(self, data, **kwargs):
        content = JSONRenderer().render(data)
        kwargs['content_type'] = 'application/json'
        super(JSONResponse, self).__init__(content, **kwargs)

@csrf_exempt
def task_list(request):
    if request.method == 'GET':
        task = TaskManagement.objects.all()
        task_serializer = TaskMngSerializer(task, many=True)
        return JSONResponse(task_serializer.data)

    elif request.method == 'POST':
        task_data = JSONParser().parse(request)
        task_serializer = TaskMngSerializer(data=task_data)
        if task_serializer.is_valid():
            task_serializer.save()
            return JSONResponse(task_serializer.data, \
                                status=status.HTTP_201_CREATED)
        return JSONResponse(task_serializer.errors, \
                            status = status.HTTP_400_BAD_REQUEST)

@csrf_exempt
def task_detail(request, pk):
    try:
        task = TaskManagement.objects.get(pk=pk)
    except TaskManagement.DoesNotExist:
        return HttpResponse(status=status.HTTP_404_NOT_FOUND)

    if request.method == 'GET':
        task_serializer = TaskMngSerializer(task)
        return JSONResponse(task_serializer.data)

    elif request.method == 'PUT':
        task_data = JSONParser().parse(request)
        task_serializer = TaskMngSerializer(task, data=task_data)
        if task_serializer.is_valid():
            task_serializer.save()
            return JSONResponse(task_serializer.data)
        return JSONResponse(task_serializer.errors, \
                            status=status.HTTP_400_BAD_REQUESTS)

    elif request.method == 'DELETE':
        task.delete()
        return HttpResponse(status=status.HTTP_204_NO_CONTENT)

```