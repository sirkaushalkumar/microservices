# My First Microservices Proof of Concepts Research

Hey there,

I am writing to inform this this is my first microservices assignment. To make use of the repository, please follow the follow steps:

> To run the microservices, one needs to have node (node.js) and git setup on the machine.

To clone the repository use the command:

`$ git clone https://github.com/sirkaushalkumar/microservices.git`

After Cloning follow the follow commands

```bash
$ npm install -g express path body-parser request
$ cd microservices
$ node ./heroes/heroes.js 8081
$ node threats/threats.js 8082
```
This will setup the application and you can continue to test the APIs:

One can check few APIs using newman by running the following command

```bash
$ newman run microservicescollection.json
```

A sample JSON is as follows:

```json
{
	"item": [
		{
			"name": "localhost:8081/heroes",
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "localhost:8081/heroes",
					"host": [
						"localhost"
					],
					"port": "8081",
					"path": [
						"heroes"
					]
				}
			},
			"response": []
		},
		{
			"name": "localhost:8081/powers",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {",
							"    pm.response.to.have.status(200);",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "localhost:8081/powers",
					"host": [
						"localhost"
					],
					"port": "8081",
					"path": [
						"powers"
					]
				}
			},
			"response": []
		},
		{
			"name": "localhost:8082/threats",
			"protocolProfileBehavior": {
				"disableBodyPruning": true
			},
			"request": {
				"method": "GET",
				"header": [
					{
						"key": "Content-Type",
						"name": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\"heroId\": 1, \"threatId\": 1}"
				},
				"url": {
					"raw": "localhost:8082/threats",
					"host": [
						"localhost"
					],
					"port": "8082",
					"path": [
						"threats"
					]
				}
			},
			"response": []
		},
		{
			"name": "localhost:8082/assignment",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Content-Type",
						"name": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"heroId\": 1,\n    \"threatId\": 1\n}"
				},
				"url": {
					"raw": "localhost:8082/assignment",
					"host": [
						"localhost"
					],
					"port": "8082",
					"path": [
						"assignment"
					]
				}
			},
			"response": []
		},
		{
			"name": "localhost:8081/powers",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							""
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"url": {
					"raw": "localhost:8081/hero/4",
					"host": [
						"localhost"
					],
					"port": "8081",
					"path": [
						"hero",
						"4"
					]
				}
			},
			"response": []
		}
	]
}
```


**Thanks for stopping by**

<!-- I remain with thanks and regards, <br/>
Kaushal Kumar -->