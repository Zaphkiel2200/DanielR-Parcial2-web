DANIEL FELIPER RIVAS ULCHUR - A00405514
|THE REQUESTS|THE BODY|THE RESULT|

|GET http://localhost:3003/api/reservations||200|
|GET http://localhost:3003/api/rooms||200|
|GET http://localhost:3003/api/reservations/1||200|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "test room",<br />  "participants": 9,<br />  "roomId": 2<br />}|201|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "test room",<br />  "participants": "9",<br />  "roomId": 2<br />}|400|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "Invalid extra property",<br />  "participants": 6,<br />  "roomId": 1,<br />  "status": "cancelled"<br />}|400|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "Unknown room",<br />  "participants": 6,<br />  "roomId": 999999999<br />}|404|
|PATCH http://localhost:3003/api/reservations/1/cancel||200|
|GET http://localhost:3003/api/reservations/1||200|
|PATCH http://localhost:3003/api/reservations/1/cancel||409|
|PATCH http://localhost:3003/api/reservations/abc/cancel||400|
|PATCH http://localhost:3003/api/reservations/999999999/cancel||404|

Tests:       3 passed, 3 total

Time:        1.50 s, estimated 2 s
