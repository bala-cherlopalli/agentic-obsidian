

```{
    "fieldName": "lossType",
    "type": "object",
    "enumUrl": "/domains/RMS/tablespace/System/entities/CyberLossType/values?fields=id,name",
"enumFieldMapping":[
  {
    "fieldName": "id",
    "enumField": "id"
  },
  {
    "fieldName": "name",
    "enumField": "name"
  }],
    "metadata": {
      "required": true,
      "readOnly": false,
      "nullable": false,
      "primaryKey": false,
      "hidden": false,
      "appDisplayDetails": {}
    },
    "properties": [
      {
        "fieldName": "id",
        "type": "integer",
        "databasePath": "cyber.policycoverage.losstype",
        "fieldDescription": "Loss type code",
        "appDisplay": false,
        "metadata": {
          "required": true,
          "readOnly": false,
          "nullable": false,
          "primaryKey": false,
          "hidden": false,
          "default": 0,
          "sortable": true,
          "filterable": true,
          "filterOperators": [
            "=",
            "!=",
            "IN",
            "NOT IN",
            "IS NULL",
            "IS NOT NULL"
          ],
          "apiValidationRules": [
            {
              "ruleType": "metadata_validation",
              "message": "{{fieldName}} does not match the metadata definition: {{metadata.property}}"
            }
          ]
        }
      },
      {
        "fieldName": "name",
        "type": "string",
        "databasePath": "cyber.policycoverage.losstype",
        "fieldDescription": "Loss type code",
        "appDisplay": true,
        "metadata": {
          "required": false,
          "readOnly": true,
          "nullable": false,
          "primaryKey": false,
          "hidden": false,
          "default": "",
          "sortable": true,
          "filterable": true,
          "filterOperators": [
            "=",
            "!=",
            "IN",
            "NOT IN",
            "IS NULL",
            "IS NOT NULL"
          ],
          "appDisplayDetails": {
            "ValidationString": "",
            "label": "Coverage",
            "width": 150,
            "group": 1,
            "columnOrder": 1
          },
          "apiValidationRules": [
            {
              "ruleType": "metadata_validation",
              "message": "{{fieldName}} does not match the metadata definition: {{metadata.property}}"
            }
          ]
        }
      }
    ]
  }
 ```


```

{
  "fieldName": "lossType",
  "type": "object",
  "enumMapping": [
    {
      "id": 0,
      "name": "a"
    },
    {
      "id": 1,
      "name": "b"
    },
    {
      "id": 2,
      "name": "c"
    },
    {
      "id": 3,
      "name": "d"
    }
  ],
  "metadata": {
    "required": true,
    "readOnly": false,
    "nullable": false,
    "primaryKey": false,
    "hidden": false,
    "appDisplayDetails": {} //upto anilesh if he wish to keep this
  },
  "properties": [
    {
      "fieldName": "id",
      "type": "integer",
      "databasePath": "cyber.policycoverage.losstype",
      "fieldDescription": "Loss type code",
      "appDisplay": false,
      "metadata": {
        "required": true,
        "readOnly": false,
        "nullable": false,
        "primaryKey": false,
        "hidden": false,
        "default": 0,
        "sortable": true,
        "filterable": true,
        "filterOperators": [
          "=",
          "!=",
          "IN",
          "NOT IN",
          "IS NULL",
          "IS NOT NULL"
        ],
        "apiValidationRules": [
          {
            "ruleType": "metadata_validation",
            "message": "{{fieldName}} does not match the metadata definition: {{metadata.property}}"
          }
        ]
      }
    },
    {
      "fieldName": "name",
      "type": "string",
      "fieldDescription": "Loss type Id",
      "appDisplay": true,
      "metadata": {
        "required": false,
        "readOnly": true,
        "nullable": false,
        "primaryKey": false,
        "hidden": false,
        "default": "",
        "sortable": true,
        "filterable": true,
        "filterOperators": [
          "=",
          "!=",
          "IN",
          "NOT IN",
          "IS NULL",
          "IS NOT NULL"
        ],
        "appDisplayDetails": {
          "ValidationString": "",
          "label": "Coverage",
          "width": 150,
          "group": 1,
          "columnOrder": 1
        },
        "apiValidationRules": [
          {
            "ruleType": "metadata_validation",
            "message": "{{fieldName}} does not match the metadata definition: {{metadata.property}}"
          }
        ]
      }
    }
  ]
}
 ```