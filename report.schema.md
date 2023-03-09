# 



<table>
<tbody>

<tr><th>$schema</th><td>http://json-schema.org/draft-06/schema#</td></tr>
</tbody>
</table>

## Properties

<table><thead><tr><th colspan="2">Name</th><th>Type</th></tr></thead><tbody></tbody></table>



<hr />







<hr />

## Schema
```
{
    "$schema": "http://json-schema.org/draft-06/schema#",
    "$ref": "#/definitions/Report",
    "definitions": {
        "Report": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "account_statements": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/AccountStatement"
                    }
                }
            },
            "required": [
                "account_statements"
            ],
            "title": "Report"
        },
        "AccountStatement": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "bank": {
                    "$ref": "#/definitions/Bank"
                },
                "bic": {
                    "$ref": "#/definitions/Bic"
                },
                "name": {
                    "$ref": "#/definitions/Name"
                },
                "firstname_1": {
                    "type": "string"
                },
                "familyname_1": {
                    "type": "string"
                },
                "firstname_2": {
                    "type": "string"
                },
                "familyname_2": {
                    "type": "string"
                },
                "address": {
                    "$ref": "#/definitions/Address"
                },
                "accounts": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/Account"
                    }
                },
                "deferred_debit_accounts": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/DeferredDebitAccount"
                    }
                }
            },
            "required": [
                "accounts",
                "address",
                "bank",
                "name"
            ],
            "title": "AccountStatement"
        },
        "Account": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "number": {
                    "type": "string"
                },
                "type": {
                    "$ref": "#/definitions/Bank"
                },
                "operations": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/AccountOperation"
                    }
                },
                "balances": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/Balance"
                    }
                },
                "sum_of_ins_and_outs": {
                    "type": "number"
                }
            },
            "required": [
                "balances",
                "number",
                "operations",
                "sum_of_ins_and_outs",
                "type"
            ],
            "title": "Account"
        },
        "Balance": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "date": {
                    "type": "string"
                },
                "format": {
                    "$ref": "#/definitions/Format"
                },
                "amount": {
                    "type": "number"
                },
                "cropPosition": {
                    "type": "array",
                    "items": {
                        "type": "integer"
                    }
                },
                "verticalPosition": {
                    "type": "integer"
                },
                "number_of_loans": {
                    "type": "integer"
                },
                "sum_of_loans_amounts": {
                    "type": "number"
                },
                "number_of_atypical_operations": {
                    "type": "integer"
                },
                "sum_of_atypical_operations_amounts": {
                    "type": "integer"
                },
                "sum_of_salaries": {
                    "type": "number"
                },
                "sum_of_bank_fees_refunds": {
                    "type": "integer"
                },
                "sum_credit": {
                    "type": "number"
                },
                "sum_debit": {
                    "type": "number"
                },
                "evolution": {
                    "type": "number"
                },
                "month": {
                    "type": "integer"
                },
                "year": {
                    "type": "integer"
                },
                "aggregates_by_category": {
                    "$ref": "#/definitions/AggregatesByCategory"
                },
                "pageNum": {
                    "type": "integer"
                }
            },
            "required": [
                "aggregates_by_category",
                "amount",
                "cropPosition",
                "date",
                "evolution",
                "format",
                "month",
                "number_of_atypical_operations",
                "number_of_loans",
                "sum_credit",
                "sum_debit",
                "sum_of_atypical_operations_amounts",
                "sum_of_bank_fees_refunds",
                "sum_of_loans_amounts",
                "sum_of_salaries",
                "verticalPosition",
                "year"
            ],
            "title": "Balance"
        },
        "AggregatesByCategory": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "SORTIES": {
                    "$ref": "#/definitions/Sorties"
                },
                "CHARGES FIXES": {
                    "$ref": "#/definitions/ChargesFixes"
                },
                "ENTRÉES": {
                    "$ref": "#/definitions/Entres"
                },
                "RESSOURCES": {
                    "$ref": "#/definitions/Ressources"
                },
                "CRÉDITS": {
                    "$ref": "#/definitions/Crdits"
                }
            },
            "required": [],
            "title": "AggregatesByCategory"
        },
        "ChargesFixes": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                },
                "sub_categories": {
                    "$ref": "#/definitions/CHARGESFIXESSubCategories"
                }
            },
            "required": [
                "sub_categories",
                "sum_of_operations"
            ],
            "title": "ChargesFixes"
        },
        "CHARGESFIXESSubCategories": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "ÉNERGIE": {
                    "$ref": "#/definitions/AssuranceDePrts"
                },
                "ASSURANCE DE PRÊTS": {
                    "$ref": "#/definitions/AssuranceDePrts"
                },
                "AUTRES CHARGES RÉGULIÈRES": {
                    "$ref": "#/definitions/AssuranceDePrts"
                }
            },
            "required": [],
            "title": "CHARGESFIXESSubCategories"
        },
        "AssuranceDePrts": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                }
            },
            "required": [
                "sum_of_operations"
            ],
            "title": "AssuranceDePrts"
        },
        "Crdits": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                },
                "sub_categories": {
                    "$ref": "#/definitions/CRDITSSubCategories"
                }
            },
            "required": [
                "sub_categories",
                "sum_of_operations"
            ],
            "title": "Crdits"
        },
        "CRDITSSubCategories": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "AUTRES CRÉDITS": {
                    "$ref": "#/definitions/AssuranceDePrts"
                }
            },
            "required": [
                "AUTRES CRÉDITS"
            ],
            "title": "CRDITSSubCategories"
        },
        "Entres": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                },
                "sub_categories": {
                    "$ref": "#/definitions/ENTRESSubCategories"
                }
            },
            "required": [
                "sub_categories",
                "sum_of_operations"
            ],
            "title": "Entres"
        },
        "ENTRESSubCategories": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "AUTRES ENTRÉES": {
                    "$ref": "#/definitions/AssuranceDePrts"
                }
            },
            "required": [
                "AUTRES ENTRÉES"
            ],
            "title": "ENTRESSubCategories"
        },
        "Ressources": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                },
                "sub_categories": {
                    "$ref": "#/definitions/RESSOURCESSubCategories"
                }
            },
            "required": [
                "sub_categories",
                "sum_of_operations"
            ],
            "title": "Ressources"
        },
        "RESSOURCESSubCategories": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "SALAIRES": {
                    "$ref": "#/definitions/AssuranceDePrts"
                },
                "ALLOCATIONS CAF": {
                    "$ref": "#/definitions/AssuranceDePrts"
                }
            },
            "required": [],
            "title": "RESSOURCESSubCategories"
        },
        "Sorties": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "sum_of_operations": {
                    "type": "number"
                },
                "sub_categories": {
                    "$ref": "#/definitions/SORTIESSubCategories"
                }
            },
            "required": [
                "sub_categories",
                "sum_of_operations"
            ],
            "title": "Sorties"
        },
        "SORTIESSubCategories": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "AUTRES SORTIES": {
                    "$ref": "#/definitions/AssuranceDePrts"
                },
                "FRAIS BANCAIRES": {
                    "$ref": "#/definitions/AssuranceDePrts"
                }
            },
            "required": [],
            "title": "SORTIESSubCategories"
        },
        "AccountOperation": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "libelle": {
                    "type": "string"
                },
                "date": {
                    "type": "string"
                },
                "category": {
                    "$ref": "#/definitions/Category"
                },
                "subCategory": {
                    "$ref": "#/definitions/SubCategory"
                },
                "amount": {
                    "type": "number"
                },
                "amountConfidence": {
                    "type": "integer"
                },
                "cropPosition": {
                    "type": "array",
                    "items": {
                        "type": "integer"
                    }
                },
                "verticalPosition": {
                    "type": "integer"
                },
                "typePayment": {
                    "$ref": "#/definitions/TypePayment"
                },
                "pageNum": {
                    "type": "integer"
                }
            },
            "required": [
                "amount",
                "amountConfidence",
                "category",
                "cropPosition",
                "date",
                "libelle",
                "subCategory",
                "typePayment",
                "verticalPosition"
            ],
            "title": "AccountOperation"
        },
        "DeferredDebitAccount": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "number": {
                    "type": "string"
                },
                "date": {
                    "$ref": "#/definitions/Date"
                },
                "totalAmount": {
                    "type": "number"
                },
                "operations": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/DeferredDebitAccountOperation"
                    }
                }
            },
            "required": [
                "date",
                "number",
                "operations",
                "totalAmount"
            ],
            "title": "DeferredDebitAccount"
        },
        "DeferredDebitAccountOperation": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "libelle": {
                    "type": "string"
                },
                "date": {
                    "$ref": "#/definitions/Date"
                },
                "category": {
                    "$ref": "#/definitions/Category"
                },
                "subCategory": {
                    "$ref": "#/definitions/SubCategory"
                },
                "amount": {
                    "type": "number"
                },
                "amountConfidence": {
                    "type": "array",
                    "items": {
                        "type": "integer"
                    }
                },
                "pageNum": {
                    "type": "integer"
                },
                "verticalPosition": {
                    "type": "integer"
                },
                "dateOp": {
                    "type": "string"
                }
            },
            "required": [
                "amount",
                "amountConfidence",
                "category",
                "date",
                "dateOp",
                "libelle",
                "pageNum",
                "subCategory",
                "verticalPosition"
            ],
            "title": "DeferredDebitAccountOperation"
        },
        "Format": {
            "type": "string",
            "title": "Format"
        },
        "Category": {
            "type": "string",
            "title": "Category"
        },
        "SubCategory": {
            "type": "string",
            "title": "SubCategory"
        },
        "TypePayment": {
            "type": "string",
            "title": "TypePayment"
        },
        "Bank": {
            "type": "string",
            "title": "Bank"
        },
        "Address": {
            "type": "string",
            "title": "Address"
        },
        "Bic": {
            "type": "string",
            "title": "Bic"
        },
        "Date": {
            "type": "string",
            "title": "Date"
        },
        "Name": {
            "type": "string",
            "title": "Name"
        }
    }
}
```


