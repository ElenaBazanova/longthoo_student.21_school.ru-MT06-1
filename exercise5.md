## Знакомство с функционалом Swagger

#### Activities

**1. GET​/api​/v1​/Activities**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities
- Заголовки запроса – accept: text/plain; v=1.0
- Тело запроса отсутстует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 1,
    "idBook": 1,
    "firstName": "First Name 1",
    "lastName": "Last Name 1"
  },
  ...
  {
    "id": 603,
    "idBook": 200,
    "firstName": "First Name 603",
    "lastName": "Last Name 603"
  }
]
```

**2. POST​/api​/v1​/Activities положительный**
- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**3. POST​/api​/v1​/Activities Отрицательный**
- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0" 
- Тело запроса:
```
{
  "id": 123456789987456321,
  "title": "string",
  "dueDate": "2023-06-08T16:44:53.199Z",
  "completed": true
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-3e01610bfb2dac439322bbefa89dc103-d136fd8bd174bb45-00",
  "errors": {
    "$.id": [
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 24."
    ]
  }
}
```

**4. GET​/api​/v1​/Activities​/1 Положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities/1 
- Заголовки запроса – "accept: text/plain; v=1.0" 
- Тело запроса отсутствует
- Статус-код ответа – 200 
- Тело ответа:
```
{
  "id": 1,
  "title": "Activity 1",
  "dueDate": "2023-06-08T17:50:56.4622233+00:00",
  "completed": false
}
```

**5. GET​/api​/v1​/Activities​/112345678987654321 Отрицательный**
- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities/12345678987654321
- Заголовки запроса – accept: text/plain; v=1.0
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-73626c5424f3a642a18ab0f267c3a2ed-17eea5e9f309b24c-00",
  "errors": {
    "id": [
      "The value '12345678987654321' is not valid."
    ]
  }
}
```

**6. PUT​/api​/v1​/Activities​/1 положительный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities/1
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0" 
- Тело запроса:
```
{
  "id": 1,
  "title": "string",
  "dueDate": "2023-06-08T17:01:37.626Z",
  "completed": true
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 1,
  "title": "string",
  "dueDate": "2023-06-08T17:01:37.626Z",
  "completed": true
}
```

**7. PUT​/api​/v1​/Activities​/147852369123 Отрицательный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities/147852369123 
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 147852369123,
  "title": "string",
  "dueDate": "2023-06-08T17:01:37.626Z",
  "completed": true
}
```
- Статус-код ответа – 400 Error: Bad Request 
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-d1692ab4a4f4fb4493ed8ce57f3e9380-60099645026f064d-00",
  "errors": {
    "id": [
      "The value '147852369123' is not valid."
    ],
    "$.id": [
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 18."
    ]
  }
}
```

**8. DELETE​/api​/v1​/Activities​/1**

- HTTP-метод – DELETE
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Activities/1
- Заголовки запроса – "accept: */*" 
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа отсутствует


#### Authors

**9. GET​/api​/v1​/Authors**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 1,
    "idBook": 1,
    "firstName": "First Name 1",
    "lastName": "Last Name 1"
  },
  ...
  {
    "id": 588,
    "idBook": 200,
    "firstName": "First Name 588",
    "lastName": "Last Name 588"
  }
]
```

**10. POST​/api​/v1​/Authors Положительный** 

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**11. POST​/api​/v1​/Authors Отрицательный** 

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 11111111111,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа – 400 Error: Bad Request 
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-81e25f1768d5c740909038c3a2baf20b-63fc0e49b37f9145-00",
  "errors": {
    "$.id": [
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 17."
    ]
  }
}
```

**12. GET​/api​/v1​/Authors​/authors​/books​/1 Положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/1
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200 
- Тело ответа:
```
[
  {
    "id": 1,
    "idBook": 1,
    "firstName": "First Name 1",
    "lastName": "Last Name 1"
  },
  {
    "id": 2,
    "idBook": 1,
    "firstName": "First Name 2",
    "lastName": "Last Name 2"
  }
]
```

**13. GET​/api​/v1​/Authors​/authors​/books​/112233445566 Отрицательный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/112233445566
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-b639d662fb36384599741538e9160bf9-c9ebfe38229a594d-00",
  "errors": {
    "idBook": [
      "The value '112233445566' is not valid."
    ]
  }
}
```

**14. GET​/api​/v1​/Authors​/5 положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/5
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 5,
  "idBook": 2,
  "firstName": "First Name 5",
  "lastName": "Last Name 5"
}
```

**15. GET​/api​/v1​/Authors​/555444666888 Отрицательный**

- HTTP-метод – GET​
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/555444666888
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request 
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-d4df63fd81c7654692708abcadd1c0ec-4ad675a9ac52d043-00",
  "errors": {
    "id": [
      "The value '555444666888' is not valid."
    ]
  }
}
```

**16. PUT​/api​/v1​/Authors​/0 положительный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/0
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0" 
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:

```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**17. PUT​/api​/v1​/Authors​/555666444888 Отрицательный**
- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/555666444888
- Заголовки запроса – "accept: text/plain; v=1.0" "Content-Type: application/json; v=1.0" 
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-a848faad7396ee45afa3985146da802a-0e1ddddcb9be204f-00",
  "errors": {
    "id": [
      "The value '555666444888' is not valid."
    ]
  }
}
```

**18. DELETE​/api​/v1​/Authors​/55 положительный**

- HTTP-метод – DELETE
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Authors/55
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа отсутствует


#### Books

**19. GET​/api​/v1​/Books**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 1,
    "title": "Book 1",
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "pageCount": 100,
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "publishDate": "2023-06-07T18:53:21.2578677+00:00"
  },
  ...
  {
    "id": 200,
    "title": "Book 200",
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "pageCount": 20000,
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "publishDate": "2022-11-20T18:53:21.2707523+00:00"
  }
]
```

**20. POST​/api​/v1​/Books Положительный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса – "accept: */*" "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T18:55:01.521Z"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T18:55:01.521Z"
}
```

**21. POST​/api​/v1​/Books Отрицательный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": A,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T18:55:01.521Z"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-7638686c2549ef4db451cf055e412b9f-7f56efbca220bb42-00",
  "errors": {
    "$.id": [
      "'A' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
    ]
  }
}
```

**22. GET​/api​/v1​/Books​/1 положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books/1
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 1,
  "title": "Book 1",
  "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
  "pageCount": 100,
  "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
  "publishDate": "2023-06-07T18:59:41.4269049+00:00"
}
```

**23. GET​/api​/v1​/Books​/3214659855 Отрицательный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books/3214659855
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-afef77ee0a196b4a80c2fb53496fe887-6cd62eb89a16a649-00",
  "errors": {
    "id": [
      "The value '3214659855' is not valid."
    ]
  }
}
```

**24. PUT​/api​/v1​/Books​/0 положительный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books/0
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T19:05:21.160Z"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T19:05:21.16Z"
}
```

**25. PUT​/api​/v1​/Books​/985124735685 Отрицательный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books/985124735685
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-06-08T19:05:21.160Z"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-b1cf2922671bf0459cbc8e9b0e2e07a6-4dd9c36c41c4fb4b-00",
  "errors": {
    "id": [
      "The value '985124735685' is not valid."
    ]
  }
}
```

**26. DELETE​/api​/v1​/Books​/1**

- HTTP-метод – DELETE
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Books/1
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа отсутствует


#### CoverPhotos

**27. GET​/api​/v1​/CoverPhotos**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 1,
    "idBook": 1,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
  },
  ...
  {
    "id": 200,
    "idBook": 200,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 200&w=250&h=350"
  }
]
```

**28. POST​/api​/v1​/CoverPhotos Положительный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos 
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```

**29. POST​/api​/v1​/CoverPhotos Отрицательный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса – "accept: text/plain; v=1.0"  "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 666888777555,
  "idBook": 0,
  "url": "string"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-68ad16ae9009df4aa201d473a9538d6d-af2ddb7adfa91545-00",
  "errors": {
    "$.id": [
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 18."
    ]
  }
}
```

**30. GET​/api​/v1​/CoverPhotos​/books​/covers​/10 Положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/10
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 10,
    "idBook": 10,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 10&w=250&h=350"
  }
]
```

**31. GET​/api​/v1​/CoverPhotos​/books​/covers​/10000100010 Отрицательный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/10000100010
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-f4a31e6dad997c478a65c551acf514cb-7fde88d98f00434d-00",
  "errors": {
    "idBook": [
      "The value '10000100010' is not valid."
    ]
  }
}
```

**32. GET​/api​/v1​/CoverPhotos​/50 Положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/50
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 50,
  "idBook": 50,
  "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 50&w=250&h=350"
}
```

**33. GET​/api​/v1​/CoverPhotos​/500000405500 Отрицательный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/500000405500
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-614e524bc3a6b34aaf9e8cb015818d83-6642ca7d58898a48-00",
  "errors": {
    "id": [
      "The value '500000405500' is not valid."
    ]
  }
}
```

**34. PUT​/api​/v1​/CoverPhotos​/85 Положительный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/85
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```

**35. PUT​/api​/v1​/CoverPhotos​/8578954512**

- HTTP-метод – PUT​
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/8578954512
- Заголовки запроса – "accept: text/plain; v=1.0"   "Content-Type: application/json; v=1.0"
- Тело запроса:
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-2c83388076445c429702db9b11f3ce46-7a6435a0b52a824d-00",
  "errors": {
    "id": [
      "The value '8578954512' is not valid."
    ]
  }
}
```

**36. DELETE​/api​/v1​/CoverPhotos​/1**

- HTTP-метод – DELETE
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа отсутствует


#### Users

**37. GET​/api​/v1​/Users**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса – "accept: text/plain; v=1.0"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
[
  {
    "id": 1,
    "userName": "User 1",
    "password": "Password1"
  },
  ...
  {
    "id": 10,
    "userName": "User 10",
    "password": "Password10"
  }
]
```

**38. POST​/api​/v1​/Users Положительный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```

**39. POST​/api​/v1​/Users Отрицательный**

- HTTP-метод – POST
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 4553849533,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-cf2eea3343763c458612a30e37c626c7-53350e826dac7841-00",
  "errors": {
    "$.id": [
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 16."
    ]
  }
}
```

**40. GET​/api​/v1​/Users​/1 Положительный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users/1
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 1,
  "userName": "User 1",
  "password": "Password1"
}
```

**41. GET​/api​/v1​/Users​/04595832597 Отрицательный**

- HTTP-метод – GET
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users/04595832597
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-eec59da0dfbf7e418b39bc8dace48960-a85f2fcc7be2bb40-00",
  "errors": {
    "id": [
      "The value '04595832597' is not valid."
    ]
  }
}
```

**42. PUT​/api​/v1​/Users​/1 Положительный**

- HTTP-метод – PUT
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users/1
- Заголовки запроса – "accept: */*"   "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа – 200
- Тело ответа:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```

**43. PUT​/api​/v1​/Users​/2348549518 Отрицательный**

- HTTP-метод – PUT​
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users/2348549518
- Заголовки запроса – "accept: */*" "Content-Type: application/json; v=1.0"
- Тело запроса:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа – 400 Error: Bad Request
- Тело ответа:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-3bc965af2fa5054aa5dc90dbf9f856e3-61310cbb7e5e1d47-00",
  "errors": {
    "id": [
      "The value '2348549518' is not valid."
    ]
  }
}
```

**44. DELETE​/api​/v1​/Users​/1**

- HTTP-метод – DELETE
- Полный URL запроса – https://fakerestapi.azurewebsites.net/api/v1/Users/1
- Заголовки запроса – "accept: */*"
- Тело запроса отсутствует
- Статус-код ответа – 200
- Тело ответа отсутствует
