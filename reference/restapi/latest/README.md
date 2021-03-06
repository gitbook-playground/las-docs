#### GET /assets





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "assets",
  "required": [
    "assets"
  ],
  "type": "object",
  "properties": {
    "assets": {
      "type": "array",
      "items": {
        "required": [
          "assetId",
          "description",
          "name"
        ],
        "type": "object",
        "properties": {
          "assetId": {
            "pattern": "^las:asset:[a-f0-9]{32}$",
            "type": "string"
          },
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "description": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "content": {
            "minLength": 1,
            "type": "string"
          }
        },
        "additionalProperties": false
      }
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


#### POST /assets





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /assets",
  "required": [
    "content"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "asset",
  "required": [
    "assetId",
    "description",
    "name"
  ],
  "type": "object",
  "properties": {
    "assetId": {
      "pattern": "^las:asset:[a-f0-9]{32}$",
      "type": "string"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### GET /assets/{assetId}


| Path name | Path value |
| --- | --- |
| assetId | Id of asset on the form las:asset:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "asset",
  "required": [
    "assetId",
    "description",
    "name"
  ],
  "type": "object",
  "properties": {
    "assetId": {
      "pattern": "^las:asset:[a-f0-9]{32}$",
      "type": "string"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### PATCH /assets/{assetId}


| Path name | Path value |
| --- | --- |
| assetId | Id of asset on the form las:asset:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /assets/assetId",
  "minProperties": 1,
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "asset",
  "required": [
    "assetId",
    "description",
    "name"
  ],
  "type": "object",
  "properties": {
    "assetId": {
      "pattern": "^las:asset:[a-f0-9]{32}$",
      "type": "string"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### POST /batches





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /batches",
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "batch",
  "required": [
    "batchId",
    "description",
    "name"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "batchId": {
      "pattern": "^las:batch:[a-f0-9]{32}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### DELETE /documents





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| consentId | Id of consent on the form las:consent:&lt;hex&gt; |





##### Response body JSON Schema
```json
{
  "title": "documents",
  "required": [
    "documents"
  ],
  "type": "object",
  "properties": {
    "consentId": {
      "type": "array",
      "items": {
        "pattern": "^las:consent:[a-f0-9]{32}$",
        "type": "string"
      }
    },
    "documents": {
      "type": "array",
      "items": {
        "required": [
          "contentType",
          "documentId"
        ],
        "type": "object",
        "properties": {
          "groundTruth": {
            "type": "array",
            "items": {
              "required": [
                "label",
                "value"
              ],
              "type": "object",
              "properties": {
                "label": {
                  "maxLength": 36,
                  "minLength": 1,
                  "pattern": "^[0-9A-Za-z_]+$",
                  "type": "string"
                },
                "value": {
                  "anyOf": [
                    {
                      "maxLength": 64,
                      "minLength": 1,
                      "type": "string",
                      "nullable": true
                    },
                    {
                      "type": "boolean"
                    }
                  ]
                }
              },
              "additionalProperties": false
            }
          },
          "consentId": {
            "pattern": "^las:consent:[a-f0-9]{32}$",
            "type": "string"
          },
          "inferenceTime": {
            "minimum": 0,
            "type": "number"
          },
          "documentId": {
            "pattern": "^las:document:[a-f0-9]{32}$",
            "type": "string"
          },
          "batchId": {
            "pattern": "^las:batch:[a-f0-9]{32}$",
            "type": "string"
          },
          "contentType": {
            "type": "string",
            "enum": [
              "application/pdf",
              "image/jpeg",
              "image/png",
              "image/tiff"
            ]
          },
          "updated": {
            "minimum": 1,
            "type": "integer"
          },
          "content": {
            "minLength": 1,
            "type": "string"
          },
          "predictions": {
            "type": "array",
            "items": {
              "required": [
                "confidence",
                "label",
                "value"
              ],
              "type": "object",
              "properties": {
                "confidence": {
                  "maximum": 1,
                  "minimum": 0,
                  "type": "number"
                },
                "label": {
                  "maxLength": 36,
                  "minLength": 1,
                  "pattern": "^[0-9A-Za-z_]+$",
                  "type": "string"
                },
                "value": {
                  "maxLength": 64,
                  "minLength": 1,
                  "type": "string",
                  "nullable": true
                }
              },
              "additionalProperties": false
            }
          }
        },
        "additionalProperties": false
      }
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "batchId": {
      "type": "array",
      "items": {
        "pattern": "^las:batch:[a-f0-9]{32}$",
        "type": "string"
      }
    }
  },
  "additionalProperties": false
}
```


#### GET /documents





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| batchId | Id of batch on the form las:batch:&lt;hex&gt; |
| consentId | Id of consent on the form las:consent:&lt;hex&gt; |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "documents",
  "required": [
    "documents"
  ],
  "type": "object",
  "properties": {
    "consentId": {
      "type": "array",
      "items": {
        "pattern": "^las:consent:[a-f0-9]{32}$",
        "type": "string"
      }
    },
    "documents": {
      "type": "array",
      "items": {
        "required": [
          "contentType",
          "documentId"
        ],
        "type": "object",
        "properties": {
          "groundTruth": {
            "type": "array",
            "items": {
              "required": [
                "label",
                "value"
              ],
              "type": "object",
              "properties": {
                "label": {
                  "maxLength": 36,
                  "minLength": 1,
                  "pattern": "^[0-9A-Za-z_]+$",
                  "type": "string"
                },
                "value": {
                  "anyOf": [
                    {
                      "maxLength": 64,
                      "minLength": 1,
                      "type": "string",
                      "nullable": true
                    },
                    {
                      "type": "boolean"
                    }
                  ]
                }
              },
              "additionalProperties": false
            }
          },
          "consentId": {
            "pattern": "^las:consent:[a-f0-9]{32}$",
            "type": "string"
          },
          "inferenceTime": {
            "minimum": 0,
            "type": "number"
          },
          "documentId": {
            "pattern": "^las:document:[a-f0-9]{32}$",
            "type": "string"
          },
          "batchId": {
            "pattern": "^las:batch:[a-f0-9]{32}$",
            "type": "string"
          },
          "contentType": {
            "type": "string",
            "enum": [
              "application/pdf",
              "image/jpeg",
              "image/png",
              "image/tiff"
            ]
          },
          "updated": {
            "minimum": 1,
            "type": "integer"
          },
          "content": {
            "minLength": 1,
            "type": "string"
          },
          "predictions": {
            "type": "array",
            "items": {
              "required": [
                "confidence",
                "label",
                "value"
              ],
              "type": "object",
              "properties": {
                "confidence": {
                  "maximum": 1,
                  "minimum": 0,
                  "type": "number"
                },
                "label": {
                  "maxLength": 36,
                  "minLength": 1,
                  "pattern": "^[0-9A-Za-z_]+$",
                  "type": "string"
                },
                "value": {
                  "maxLength": 64,
                  "minLength": 1,
                  "type": "string",
                  "nullable": true
                }
              },
              "additionalProperties": false
            }
          }
        },
        "additionalProperties": false
      }
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "batchId": {
      "type": "array",
      "items": {
        "pattern": "^las:batch:[a-f0-9]{32}$",
        "type": "string"
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /documents





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /documents",
  "required": [
    "content",
    "contentType"
  ],
  "type": "object",
  "properties": {
    "groundTruth": {
      "type": "array",
      "items": {
        "required": [
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "anyOf": [
              {
                "maxLength": 64,
                "minLength": 1,
                "type": "string",
                "nullable": true
              },
              {
                "type": "boolean"
              }
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "consentId": {
      "pattern": "^las:consent:[a-f0-9]{32}$",
      "type": "string"
    },
    "batchId": {
      "pattern": "^las:batch:[a-f0-9]{32}$",
      "type": "string"
    },
    "contentType": {
      "type": "string",
      "enum": [
        "application/pdf",
        "image/jpeg",
        "image/png",
        "image/tiff"
      ]
    },
    "content": {
      "minLength": 1,
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "document",
  "required": [
    "contentType",
    "documentId"
  ],
  "type": "object",
  "properties": {
    "groundTruth": {
      "type": "array",
      "items": {
        "required": [
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "anyOf": [
              {
                "maxLength": 64,
                "minLength": 1,
                "type": "string",
                "nullable": true
              },
              {
                "type": "boolean"
              }
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "consentId": {
      "pattern": "^las:consent:[a-f0-9]{32}$",
      "type": "string"
    },
    "inferenceTime": {
      "minimum": 0,
      "type": "number"
    },
    "documentId": {
      "pattern": "^las:document:[a-f0-9]{32}$",
      "type": "string"
    },
    "batchId": {
      "pattern": "^las:batch:[a-f0-9]{32}$",
      "type": "string"
    },
    "contentType": {
      "type": "string",
      "enum": [
        "application/pdf",
        "image/jpeg",
        "image/png",
        "image/tiff"
      ]
    },
    "updated": {
      "minimum": 1,
      "type": "integer"
    },
    "content": {
      "minLength": 1,
      "type": "string"
    },
    "predictions": {
      "type": "array",
      "items": {
        "required": [
          "confidence",
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "confidence": {
            "maximum": 1,
            "minimum": 0,
            "type": "number"
          },
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "maxLength": 64,
            "minLength": 1,
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### GET /documents/{documentId}


| Path name | Path value |
| --- | --- |
| documentId | Id of document on the form las:document:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "document",
  "required": [
    "contentType",
    "documentId"
  ],
  "type": "object",
  "properties": {
    "groundTruth": {
      "type": "array",
      "items": {
        "required": [
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "anyOf": [
              {
                "maxLength": 64,
                "minLength": 1,
                "type": "string",
                "nullable": true
              },
              {
                "type": "boolean"
              }
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "consentId": {
      "pattern": "^las:consent:[a-f0-9]{32}$",
      "type": "string"
    },
    "inferenceTime": {
      "minimum": 0,
      "type": "number"
    },
    "documentId": {
      "pattern": "^las:document:[a-f0-9]{32}$",
      "type": "string"
    },
    "batchId": {
      "pattern": "^las:batch:[a-f0-9]{32}$",
      "type": "string"
    },
    "contentType": {
      "type": "string",
      "enum": [
        "application/pdf",
        "image/jpeg",
        "image/png",
        "image/tiff"
      ]
    },
    "updated": {
      "minimum": 1,
      "type": "integer"
    },
    "content": {
      "minLength": 1,
      "type": "string"
    },
    "predictions": {
      "type": "array",
      "items": {
        "required": [
          "confidence",
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "confidence": {
            "maximum": 1,
            "minimum": 0,
            "type": "number"
          },
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "maxLength": 64,
            "minLength": 1,
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### PATCH /documents/{documentId}


| Path name | Path value |
| --- | --- |
| documentId | Id of document on the form las:document:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /documents/{documentId}",
  "required": [
    "groundTruth"
  ],
  "type": "object",
  "properties": {
    "groundTruth": {
      "type": "array",
      "items": {
        "required": [
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "anyOf": [
              {
                "maxLength": 64,
                "minLength": 1,
                "type": "string",
                "nullable": true
              },
              {
                "type": "boolean"
              }
            ]
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "document",
  "required": [
    "contentType",
    "documentId"
  ],
  "type": "object",
  "properties": {
    "groundTruth": {
      "type": "array",
      "items": {
        "required": [
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "anyOf": [
              {
                "maxLength": 64,
                "minLength": 1,
                "type": "string",
                "nullable": true
              },
              {
                "type": "boolean"
              }
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "consentId": {
      "pattern": "^las:consent:[a-f0-9]{32}$",
      "type": "string"
    },
    "inferenceTime": {
      "minimum": 0,
      "type": "number"
    },
    "documentId": {
      "pattern": "^las:document:[a-f0-9]{32}$",
      "type": "string"
    },
    "batchId": {
      "pattern": "^las:batch:[a-f0-9]{32}$",
      "type": "string"
    },
    "contentType": {
      "type": "string",
      "enum": [
        "application/pdf",
        "image/jpeg",
        "image/png",
        "image/tiff"
      ]
    },
    "updated": {
      "minimum": 1,
      "type": "integer"
    },
    "content": {
      "minLength": 1,
      "type": "string"
    },
    "predictions": {
      "type": "array",
      "items": {
        "required": [
          "confidence",
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "confidence": {
            "maximum": 1,
            "minimum": 0,
            "type": "number"
          },
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "maxLength": 64,
            "minLength": 1,
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### GET /logs/{logId}


| Path name | Path value |
| --- | --- |
| logId | Id of log on the form las:log:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "log",
  "required": [
    "events",
    "logId"
  ],
  "type": "object",
  "properties": {
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "logId": {
      "pattern": "^las:log:[a-f0-9]{32}$",
      "type": "string"
    },
    "events": {
      "type": "array",
      "items": {
        "type": "object"
      }
    }
  },
  "additionalProperties": false
}
```


#### GET /models





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "models",
  "required": [
    "models"
  ],
  "type": "object",
  "properties": {
    "models": {
      "type": "array",
      "items": {
        "required": [
          "description",
          "height",
          "modelId",
          "name",
          "preprocessConfig",
          "width"
        ],
        "type": "object",
        "properties": {
          "preprocessConfig": {
            "required": [
              "autoRotate",
              "imageQuality",
              "maxPages"
            ],
            "type": "object",
            "properties": {
              "maxPages": {
                "type": "integer"
              },
              "autoRotate": {
                "type": "boolean"
              },
              "imageQuality": {
                "type": "string",
                "enum": [
                  "LOW",
                  "HIGH"
                ]
              }
            },
            "additionalProperties": false
          },
          "modelId": {
            "pattern": "^las:model:[0-9A-Za-z_]+$",
            "type": "string"
          },
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "width": {
            "type": "integer"
          },
          "description": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "height": {
            "type": "integer"
          }
        },
        "additionalProperties": false
      }
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


#### GET /predictions





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "predictions",
  "required": [
    "predictions"
  ],
  "type": "object",
  "properties": {
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "predictions": {
      "type": "array",
      "items": {
        "required": [
          "documentId",
          "inferenceTime",
          "modelId",
          "predictionId",
          "predictions",
          "timestamp"
        ],
        "type": "object",
        "properties": {
          "modelId": {
            "pattern": "^las:model:[0-9A-Za-z_]+$",
            "type": "string"
          },
          "inferenceTime": {
            "minimum": 0,
            "type": "number"
          },
          "documentId": {
            "pattern": "^las:document:[a-f0-9]{32}$",
            "type": "string"
          },
          "predictionId": {
            "pattern": "^las:prediction:[a-f0-9]{32}$",
            "type": "string"
          },
          "predictions": {
            "type": "array",
            "items": {
              "required": [
                "confidence",
                "label",
                "value"
              ],
              "type": "object",
              "properties": {
                "confidence": {
                  "maximum": 1,
                  "minimum": 0,
                  "type": "number"
                },
                "label": {
                  "maxLength": 36,
                  "minLength": 1,
                  "pattern": "^[0-9A-Za-z_]+$",
                  "type": "string"
                },
                "value": {
                  "maxLength": 64,
                  "minLength": 1,
                  "type": "string",
                  "nullable": true
                }
              },
              "additionalProperties": false
            }
          },
          "timestamp": {
            "minimum": 1,
            "type": "integer"
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /predictions





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /predictions",
  "required": [
    "documentId",
    "modelId"
  ],
  "type": "object",
  "properties": {
    "modelId": {
      "pattern": "^las:model:[0-9A-Za-z_]+$",
      "type": "string"
    },
    "maxPages": {
      "maximum": 3,
      "minimum": 1,
      "type": "integer"
    },
    "documentId": {
      "pattern": "^las:document:[a-f0-9]{32}$",
      "type": "string"
    },
    "autoRotate": {
      "type": "boolean"
    },
    "imageQuality": {
      "type": "string",
      "enum": [
        "LOW",
        "HIGH"
      ]
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "prediction",
  "required": [
    "documentId",
    "inferenceTime",
    "modelId",
    "predictionId",
    "predictions",
    "timestamp"
  ],
  "type": "object",
  "properties": {
    "modelId": {
      "pattern": "^las:model:[0-9A-Za-z_]+$",
      "type": "string"
    },
    "inferenceTime": {
      "minimum": 0,
      "type": "number"
    },
    "documentId": {
      "pattern": "^las:document:[a-f0-9]{32}$",
      "type": "string"
    },
    "predictionId": {
      "pattern": "^las:prediction:[a-f0-9]{32}$",
      "type": "string"
    },
    "predictions": {
      "type": "array",
      "items": {
        "required": [
          "confidence",
          "label",
          "value"
        ],
        "type": "object",
        "properties": {
          "confidence": {
            "maximum": 1,
            "minimum": 0,
            "type": "number"
          },
          "label": {
            "maxLength": 36,
            "minLength": 1,
            "pattern": "^[0-9A-Za-z_]+$",
            "type": "string"
          },
          "value": {
            "maxLength": 64,
            "minLength": 1,
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      }
    },
    "timestamp": {
      "minimum": 1,
      "type": "integer"
    }
  },
  "additionalProperties": false
}
```


#### GET /secrets





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "secrets",
  "required": [
    "secrets"
  ],
  "type": "object",
  "properties": {
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "secrets": {
      "type": "array",
      "items": {
        "required": [
          "description",
          "name",
          "secretId"
        ],
        "type": "object",
        "properties": {
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "secretId": {
            "pattern": "^las:secret:[a-f0-9]{32}$",
            "type": "string"
          },
          "description": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /secrets





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /secrets",
  "required": [
    "data"
  ],
  "type": "object",
  "properties": {
    "data": {
      "type": "object"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "secret",
  "required": [
    "description",
    "name",
    "secretId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "secretId": {
      "pattern": "^las:secret:[a-f0-9]{32}$",
      "type": "string"
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


#### PATCH /secrets/{secretId}


| Path name | Path value |
| --- | --- |
| secretId | Id of secret on the form las:secret:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /secrets/{secretId}",
  "minProperties": 1,
  "type": "object",
  "properties": {
    "data": {
      "type": "object"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "secret",
  "required": [
    "description",
    "name",
    "secretId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "secretId": {
      "pattern": "^las:secret:[a-f0-9]{32}$",
      "type": "string"
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


#### GET /transitions





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| transitionType | manual \| docker |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "transitions",
  "required": [
    "transitions"
  ],
  "type": "object",
  "properties": {
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitions": {
      "type": "array",
      "items": {
        "required": [
          "description",
          "name",
          "transitionId",
          "transitionType"
        ],
        "type": "object",
        "properties": {
          "outputJsonSchema": {
            "type": "object"
          },
          "assets": {
            "type": "object",
            "properties": {
              "jsRemoteComponent": {
                "pattern": "^las:asset:[a-f0-9]{32}$",
                "type": "string"
              }
            },
            "additionalProperties": true
          },
          "transitionId": {
            "anyOf": [
              {
                "pattern": "^las:transition:[a-f0-9]{32}$",
                "type": "string"
              },
              {
                "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
                "type": "string"
              }
            ]
          },
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "description": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "transitionType": {
            "type": "string"
          },
          "inputJsonSchema": {
            "type": "object"
          },
          "parameters": {
            "type": "object"
          }
        },
        "additionalProperties": false
      }
    },
    "transitionType": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": [
          "docker",
          "manual"
        ]
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /transitions





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /transitions",
  "required": [
    "transitionType"
  ],
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitionType": {
      "type": "string",
      "enum": [
        "docker",
        "manual"
      ]
    },
    "inputJsonSchema": {
      "type": "object"
    },
    "parameters": {
      "anyOf": [
        {
          "required": [
            "imageUrl"
          ],
          "type": "object",
          "properties": {
            "environmentSecrets": {
              "type": "array",
              "items": {
                "pattern": "^las:secret:[a-f0-9]{32}$",
                "type": "string"
              }
            },
            "environment": {
              "type": "object",
              "additionalProperties": true
            },
            "memory": {
              "type": "integer",
              "enum": [
                512,
                1024,
                2048
              ]
            },
            "imageUrl": {
              "type": "string"
            },
            "secretId": {
              "pattern": "^las:secret:[a-f0-9]{32}$",
              "type": "string"
            },
            "cpu": {
              "type": "integer",
              "enum": [
                256
              ]
            }
          },
          "additionalProperties": false
        },
        {
          "type": "object",
          "properties": {
            "assets": {
              "type": "object",
              "properties": {
                "jsRemoteComponent": {
                  "pattern": "^las:asset:[a-f0-9]{32}$",
                  "type": "string"
                }
              },
              "additionalProperties": true
            }
          },
          "additionalProperties": false
        }
      ]
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "transition",
  "required": [
    "description",
    "name",
    "transitionId",
    "transitionType"
  ],
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "assets": {
      "type": "object",
      "properties": {
        "jsRemoteComponent": {
          "pattern": "^las:asset:[a-f0-9]{32}$",
          "type": "string"
        }
      },
      "additionalProperties": true
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitionType": {
      "type": "string"
    },
    "inputJsonSchema": {
      "type": "object"
    },
    "parameters": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


#### DELETE /transitions/{transitionId}


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "transition",
  "required": [
    "description",
    "name",
    "transitionId",
    "transitionType"
  ],
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "assets": {
      "type": "object",
      "properties": {
        "jsRemoteComponent": {
          "pattern": "^las:asset:[a-f0-9]{32}$",
          "type": "string"
        }
      },
      "additionalProperties": true
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitionType": {
      "type": "string"
    },
    "inputJsonSchema": {
      "type": "object"
    },
    "parameters": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


#### GET /transitions/{transitionId}


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "transition",
  "required": [
    "description",
    "name",
    "transitionId",
    "transitionType"
  ],
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "assets": {
      "type": "object",
      "properties": {
        "jsRemoteComponent": {
          "pattern": "^las:asset:[a-f0-9]{32}$",
          "type": "string"
        }
      },
      "additionalProperties": true
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitionType": {
      "type": "string"
    },
    "inputJsonSchema": {
      "type": "object"
    },
    "parameters": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


#### PATCH /transitions/{transitionId}


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /transitions/{transitionId}",
  "minProperties": 1,
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "inputJsonSchema": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "transition",
  "required": [
    "description",
    "name",
    "transitionId",
    "transitionType"
  ],
  "type": "object",
  "properties": {
    "outputJsonSchema": {
      "type": "object"
    },
    "assets": {
      "type": "object",
      "properties": {
        "jsRemoteComponent": {
          "pattern": "^las:asset:[a-f0-9]{32}$",
          "type": "string"
        }
      },
      "additionalProperties": true
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "transitionType": {
      "type": "string"
    },
    "inputJsonSchema": {
      "type": "object"
    },
    "parameters": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


#### GET /transitions/{transitionId}/executions


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| order | ascending \| descending |
| executionId | String |
| status | running \| succeeded \| failed \| rejected \| retry |
| maxResults | Integer representing maximum number of resources to list |
| sortBy | startTime \| endTime |





##### Response body JSON Schema
```json
{
  "title": "transition-executions",
  "required": [
    "executions",
    "transitionId"
  ],
  "type": "object",
  "properties": {
    "executions": {
      "type": "array",
      "items": {
        "required": [
          "completedBy",
          "executionId",
          "input",
          "status",
          "transitionId"
        ],
        "type": "object",
        "properties": {
          "executionId": {
            "pattern": "^las:transition-execution:[a-f0-9]{32}$",
            "type": "string"
          },
          "input": {
            "type": "object"
          },
          "transitionId": {
            "anyOf": [
              {
                "pattern": "^las:transition:[a-f0-9]{32}$",
                "type": "string"
              },
              {
                "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
                "type": "string"
              }
            ]
          },
          "startTime": {
            "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
            "type": "string",
            "nullable": true
          },
          "logId": {
            "pattern": "^las:log:[a-f0-9]{32}$",
            "type": "string",
            "nullable": true
          },
          "endTime": {
            "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
            "type": "string",
            "nullable": true
          },
          "completedBy": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "status": {
            "type": "string",
            "enum": [
              "running",
              "succeeded",
              "failed",
              "rejected",
              "retry"
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "status": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": [
          "running",
          "succeeded",
          "failed",
          "rejected",
          "retry"
        ]
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /transitions/{transitionId}/executions


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /transitions/{transitionId}/executions",
  "type": "object"
}
```


##### Response body JSON Schema
```json
{
  "title": "transition-execution",
  "required": [
    "completedBy",
    "executionId",
    "input",
    "status",
    "transitionId"
  ],
  "type": "object",
  "properties": {
    "executionId": {
      "pattern": "^las:transition-execution:[a-f0-9]{32}$",
      "type": "string"
    },
    "input": {
      "type": "object"
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "logId": {
      "pattern": "^las:log:[a-f0-9]{32}$",
      "type": "string",
      "nullable": true
    },
    "endTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "completedBy": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "status": {
      "type": "string",
      "enum": [
        "running",
        "succeeded",
        "failed",
        "rejected",
        "retry"
      ]
    }
  },
  "additionalProperties": false
}
```


#### GET /transitions/{transitionId}/executions/{executionId}


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |
| executionId | Id of execution on the form las:transition-execution:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "transition-execution",
  "required": [
    "completedBy",
    "executionId",
    "input",
    "status",
    "transitionId"
  ],
  "type": "object",
  "properties": {
    "executionId": {
      "pattern": "^las:transition-execution:[a-f0-9]{32}$",
      "type": "string"
    },
    "input": {
      "type": "object"
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "logId": {
      "pattern": "^las:log:[a-f0-9]{32}$",
      "type": "string",
      "nullable": true
    },
    "endTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "completedBy": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "status": {
      "type": "string",
      "enum": [
        "running",
        "succeeded",
        "failed",
        "rejected",
        "retry"
      ]
    }
  },
  "additionalProperties": false
}
```


#### PATCH /transitions/{transitionId}/executions/{executionId}


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |
| executionId | Id of execution on the form las:transition-execution:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH transitions/{transitionId}/executions/{executionId}",
  "type": "object",
  "properties": {
    "output": {
      "type": "object"
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "error": {
      "required": [
        "message"
      ],
      "type": "object",
      "properties": {
        "message": {
          "type": "string"
        }
      },
      "additionalProperties": false
    },
    "status": {
      "type": "string"
    }
  },
  "additionalProperties": false,
  "anyOf": [
    {
      "type": "object",
      "properties": {
        "status": {
          "type": "string",
          "enum": [
            "succeeded"
          ]
        }
      }
    },
    {
      "type": "object",
      "properties": {
        "status": {
          "type": "string",
          "enum": [
            "failed",
            "rejected",
            "retry"
          ]
        }
      }
    }
  ]
}
```


##### Response body JSON Schema
```json
{
  "title": "transition-execution",
  "required": [
    "completedBy",
    "executionId",
    "input",
    "status",
    "transitionId"
  ],
  "type": "object",
  "properties": {
    "executionId": {
      "pattern": "^las:transition-execution:[a-f0-9]{32}$",
      "type": "string"
    },
    "input": {
      "type": "object"
    },
    "transitionId": {
      "anyOf": [
        {
          "pattern": "^las:transition:[a-f0-9]{32}$",
          "type": "string"
        },
        {
          "pattern": "^las:transition:commons-[0-9A-Za-z-]+$",
          "type": "string"
        }
      ]
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "logId": {
      "pattern": "^las:log:[a-f0-9]{32}$",
      "type": "string",
      "nullable": true
    },
    "endTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "completedBy": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "status": {
      "type": "string",
      "enum": [
        "running",
        "succeeded",
        "failed",
        "rejected",
        "retry"
      ]
    }
  },
  "additionalProperties": false
}
```


#### POST /transitions/{transitionId}/executions/{executionId}/heartbeats


| Path name | Path value |
| --- | --- |
| transitionId | Id of transition on the form las:transition:&lt;hex&gt; |
| executionId | Id of execution on the form las:transition-execution:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /transitions/{transitionId}/executions/{executionId}/heartbeats",
  "type": "object"
}
```





#### GET /users





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "users",
  "required": [
    "users"
  ],
  "type": "object",
  "properties": {
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "users": {
      "type": "array",
      "items": {
        "required": [
          "email",
          "userId"
        ],
        "type": "object",
        "properties": {
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "avatar": {
            "maxLength": 131072,
            "type": "string",
            "nullable": true
          },
          "userId": {
            "pattern": "^las:user:[a-f0-9]{32}$",
            "type": "string"
          },
          "email": {
            "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
            "type": "string"
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /users





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /users",
  "required": [
    "email"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    },
    "email": {
      "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "user",
  "required": [
    "email",
    "userId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    },
    "userId": {
      "pattern": "^las:user:[a-f0-9]{32}$",
      "type": "string"
    },
    "email": {
      "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### DELETE /users/{userId}


| Path name | Path value |
| --- | --- |
| userId | Id of user on the form las:user:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "user",
  "required": [
    "email",
    "userId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    },
    "userId": {
      "pattern": "^las:user:[a-f0-9]{32}$",
      "type": "string"
    },
    "email": {
      "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### GET /users/{userId}


| Path name | Path value |
| --- | --- |
| userId | Id of user on the form las:user:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "user",
  "required": [
    "email",
    "userId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    },
    "userId": {
      "pattern": "^las:user:[a-f0-9]{32}$",
      "type": "string"
    },
    "email": {
      "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### PATCH /users/{userId}


| Path name | Path value |
| --- | --- |
| userId | Id of user on the form las:user:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /users/{userId}",
  "minProperties": 1,
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "user",
  "required": [
    "email",
    "userId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "avatar": {
      "maxLength": 131072,
      "type": "string",
      "nullable": true
    },
    "userId": {
      "pattern": "^las:user:[a-f0-9]{32}$",
      "type": "string"
    },
    "email": {
      "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### GET /workflows





| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |





##### Response body JSON Schema
```json
{
  "title": "workflows",
  "required": [
    "workflows"
  ],
  "type": "object",
  "properties": {
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "workflows": {
      "type": "array",
      "items": {
        "required": [
          "description",
          "name",
          "workflowId"
        ],
        "type": "object",
        "properties": {
          "name": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "description": {
            "maxLength": 4096,
            "type": "string",
            "nullable": true
          },
          "workflowId": {
            "pattern": "^las:workflow:[a-f0-9]{32}$",
            "type": "string"
          }
        },
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```


#### POST /workflows





| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /workflows",
  "required": [
    "specification"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "specification": {
      "required": [
        "definition"
      ],
      "type": "object",
      "properties": {
        "language": {
          "type": "string",
          "enum": [
            "ASL"
          ]
        },
        "definition": {
          "type": "object"
        },
        "version": {
          "type": "string",
          "enum": [
            "1.0.0"
          ]
        }
      },
      "additionalProperties": false
    },
    "errorConfig": {
      "required": [
        "email"
      ],
      "type": "object",
      "properties": {
        "email": {
          "pattern": "^[A-Za-z0-9][-+._A-Za-z0-9]*@([A-Za-z0-9]+\\.)+[A-Za-z]{2,}$",
          "type": "string"
        }
      },
      "additionalProperties": false
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "workflow",
  "required": [
    "description",
    "name",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### DELETE /workflows/{workflowId}


| Path name | Path value |
| --- | --- |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "workflow",
  "required": [
    "description",
    "name",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### GET /workflows/{workflowId}


| Path name | Path value |
| --- | --- |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "workflow",
  "required": [
    "description",
    "name",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### PATCH /workflows/{workflowId}


| Path name | Path value |
| --- | --- |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "PATCH /workflows/{workflowId}",
  "minProperties": 1,
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "workflow",
  "required": [
    "description",
    "name",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "name": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "description": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    }
  },
  "additionalProperties": false
}
```


#### GET /workflows/{workflowId}/executions


| Path name | Path value |
| --- | --- |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |


| Query name | Query value |
| --- | --- |
| status | running \| succeeded \| failed \| rejected \| retry |
| nextToken | String value as returned by a previous list operation |
| maxResults | Integer representing maximum number of resources to list |
| sortBy | startTime \| endTime |
| order | ascending \| descending |





##### Response body JSON Schema
```json
{
  "title": "workflow-executions",
  "required": [
    "executions",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "executions": {
      "type": "array",
      "items": {
        "required": [
          "endTime",
          "executionId",
          "input",
          "output",
          "startTime",
          "status",
          "transitionExecutions",
          "workflowId"
        ],
        "type": "object",
        "properties": {
          "transitionExecutions": {
            "type": "object"
          },
          "output": {
            "type": "object"
          },
          "executionId": {
            "pattern": "^las:workflow-execution:[a-f0-9]{32}$",
            "type": "string"
          },
          "input": {
            "type": "object"
          },
          "startTime": {
            "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
            "type": "string",
            "nullable": true
          },
          "endTime": {
            "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
            "type": "string",
            "nullable": true
          },
          "workflowId": {
            "pattern": "^las:workflow:[a-f0-9]{32}$",
            "type": "string"
          },
          "completedBy": {
            "type": "array",
            "items": {
              "anyOf": [
                {
                  "pattern": "^las:user:[a-f0-9]{32}$",
                  "type": "string"
                },
                {
                  "pattern": "^las:app-client:[a-f0-9]{32}$",
                  "type": "string"
                }
              ]
            }
          },
          "status": {
            "type": "string",
            "enum": [
              "running",
              "succeeded",
              "failed",
              "rejected",
              "retry"
            ]
          }
        },
        "additionalProperties": false
      }
    },
    "nextToken": {
      "maxLength": 4096,
      "type": "string",
      "nullable": true
    },
    "sortBy": {
      "type": "string",
      "enum": [
        "startTime",
        "endTime"
      ]
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    },
    "status": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": [
          "running",
          "succeeded",
          "failed",
          "rejected",
          "retry"
        ]
      }
    },
    "order": {
      "type": "string",
      "enum": [
        "ascending",
        "descending"
      ]
    }
  },
  "additionalProperties": false
}
```


#### POST /workflows/{workflowId}/executions


| Path name | Path value |
| --- | --- |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Content-Type | application/json |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |





##### Request body JSON Schema
```json
{
  "title": "POST /workflows/{workflowId}/executions",
  "required": [
    "input"
  ],
  "type": "object",
  "properties": {
    "input": {
      "type": "object"
    }
  },
  "additionalProperties": false
}
```


##### Response body JSON Schema
```json
{
  "title": "workflow-execution",
  "required": [
    "endTime",
    "executionId",
    "input",
    "output",
    "startTime",
    "status",
    "transitionExecutions",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "transitionExecutions": {
      "type": "object"
    },
    "output": {
      "type": "object"
    },
    "executionId": {
      "pattern": "^las:workflow-execution:[a-f0-9]{32}$",
      "type": "string"
    },
    "input": {
      "type": "object"
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "endTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    },
    "completedBy": {
      "type": "array",
      "items": {
        "anyOf": [
          {
            "pattern": "^las:user:[a-f0-9]{32}$",
            "type": "string"
          },
          {
            "pattern": "^las:app-client:[a-f0-9]{32}$",
            "type": "string"
          }
        ]
      }
    },
    "status": {
      "type": "string",
      "enum": [
        "running",
        "succeeded",
        "failed",
        "rejected",
        "retry"
      ]
    }
  },
  "additionalProperties": false
}
```


#### DELETE /workflows/{workflowId}/executions/{executionId}


| Path name | Path value |
| --- | --- |
| executionId | Id of execution on the form las:workflow-execution:&lt;hex&gt; |
| workflowId | Id of workflow on the form las:workflow:&lt;hex&gt; |


| Header name | Header value |
| --- | --- |
| Authorization | Bearer &lt;your access token here&gt; |
| x-api-key | &lt;your api key here&gt; |








##### Response body JSON Schema
```json
{
  "title": "workflow-execution",
  "required": [
    "endTime",
    "executionId",
    "input",
    "output",
    "startTime",
    "status",
    "transitionExecutions",
    "workflowId"
  ],
  "type": "object",
  "properties": {
    "transitionExecutions": {
      "type": "object"
    },
    "output": {
      "type": "object"
    },
    "executionId": {
      "pattern": "^las:workflow-execution:[a-f0-9]{32}$",
      "type": "string"
    },
    "input": {
      "type": "object"
    },
    "startTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "endTime": {
      "pattern": "^[0-9]{4}-?[0-9]{2}-?[0-9]{2} ?[0-9]{2}:?[0-9]{2}:?[0-9]{2}.?[0-9]{6}",
      "type": "string",
      "nullable": true
    },
    "workflowId": {
      "pattern": "^las:workflow:[a-f0-9]{32}$",
      "type": "string"
    },
    "completedBy": {
      "type": "array",
      "items": {
        "anyOf": [
          {
            "pattern": "^las:user:[a-f0-9]{32}$",
            "type": "string"
          },
          {
            "pattern": "^las:app-client:[a-f0-9]{32}$",
            "type": "string"
          }
        ]
      }
    },
    "status": {
      "type": "string",
      "enum": [
        "running",
        "succeeded",
        "failed",
        "rejected",
        "retry"
      ]
    }
  },
  "additionalProperties": false
}
```

