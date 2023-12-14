<!--
 ___ _            _ _    _ _    __
/ __(_)_ __  _ __| (_)__(_) |_ /_/
\__ \ | '  \| '_ \ | / _| |  _/ -_)
|___/_|_|_|_| .__/_|_\__|_|\__\___|
            |_| 
-->
![](https://docs.simplicite.io//logos/logo250.png)
* * *

`Training` module definition
============================



`TrnSupplier` business object definition
----------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `trnSupCode`                                                 | char(30)                                 | yes*     | yes       |          | -                                                                                |
| `trnSupName`                                                 | char(100)                                | yes      | yes       |          | -                                                                                |
| `trnSupPhone`                                                | phone(100)                               |          | yes       |          | -                                                                                |
| `trnSupLogo`                                                 | image                                    |          | yes       |          | -                                                                                |
| `trnSupWebsite`                                              | url(100)                                 |          | yes       |          | -                                                                                |

`TrnProduct` business object definition
---------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `trnPrdReference`                                            | char(100)                                | yes*     | yes       |          | -                                                                                |
| `trnPrdPrice`                                                | float(100, 2)                            |          | yes       |          | -                                                                                |
| `trnPrdStock`                                                | int(100)                                 |          | yes       |          | -                                                                                |
| `trnPrdName`                                                 | char(100)                                |          | yes       |          | -                                                                                |
| `trnPrdDescription`                                          | html(100)                                |          | yes       |          | -                                                                                |
| `trnPrdPicture`                                              | image                                    |          | yes       |          | -                                                                                |
| `trnPrdSupId` link to **`TrnSupplier`**                      | id                                       | yes      | yes       |          | -                                                                                |
| _Ref. `trnPrdSupId.trnSupCode`_                              | _char(30)_                               |          |           |          | -                                                                                |
| _Ref. `trnPrdSupId.trnSupName`_                              | _char(100)_                              |          |           |          | -                                                                                |

`TrnClient` business object definition
--------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `trnCliFirstName`                                            | char(100)                                | yes*     | yes       |          | -                                                                                |
| `trnCliFamilyName`                                           | char(100)                                | yes*     | yes       |          | -                                                                                |
| `trnCliMail`                                                 | email(100)                               |          | yes       |          | -                                                                                |
| `trnCliPhone`                                                | phone(100)                               |          | yes       |          | -                                                                                |
| `trnCliAddress`                                              | text(100)                                |          | yes       |          | -                                                                                |

`TrnOrder` business object definition
-------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `trnOrdNumber`                                               | char(100)                                | yes*     | yes       |          | -                                                                                |
| `trnOrdQuantity`                                             | int(100)                                 | yes      | yes       |          | -                                                                                |
| `trnOrdDate`                                                 | date                                     | yes      | yes       |          | -                                                                                |
| `trnOrdPrdId` link to **`TrnProduct`**                       | id                                       |          | yes       |          | -                                                                                |
| _Ref. `trnOrdPrdId.trnPrdReference`_                         | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `trnOrdPrdId.trnPrdPrice`_                             | _float(100, 2)_                          |          |           |          | -                                                                                |
| _Ref. `trnOrdPrdId.trnPrdStock`_                             | _int(100)_                               |          |           |          | -                                                                                |
| _Ref. `trnOrdPrdId.trnPrdName`_                              | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `trnOrdPrdId.trnPrdSupId`_                             | _id_                                     |          |           |          | -                                                                                |
| _Ref. `trnPrdSupId.trnSupCode`_                              | _char(30)_                               |          |           |          | -                                                                                |
| _Ref. `trnPrdSupId.trnSupName`_                              | _char(100)_                              |          |           |          | -                                                                                |
| `trnOrdCliId` link to **`TrnClient`**                        | id                                       |          | yes       |          | -                                                                                |
| _Ref. `trnOrdCliId.trnCliFirstName`_                         | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `trnOrdCliId.trnCliFamilyName`_                        | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `trnOrdCliId.trnCliMail`_                              | _email(100)_                             |          |           |          | -                                                                                |
| `trnOrdState`                                                | enum(10) using `TRN_ORD_STATE` list      | yes      | yes       |          | -                                                                                |

### Lists

* `TRN_ORD_STATE`
    - `PENDING` Pending
    - `CANCELED` Canceled
    - `VALIDATED` Validated
    - `SENT` Sent

