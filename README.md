# Borrow-ID-Qr
Create and Read Qr-code for borrow id
## Create Qr-code


`GET`
```
http://api.qrserver.com/v1/create-qr-code/?data=[borrow-id]&size=[pixels]x[pixels]
```

### Parameters

Data fields | Data type | Notes
---------|----------|---------
 data | Integer | None
 size | Integer | less than 100

### Request
```json http
{
  "method": "get",
  "url": "https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=1343423"
}
```
## Read Qr-code

`GET`
```
http://api.qrserver.com/v1/read-qr-code/?fileurl=[URL-encoded-webaddress]
```

### Parameters
#### fileurl
- Address (URL) of a image file accessible via Internet, containing the QR code to read (e.g. a photo).
- Format:

[URL]. The adress has to be URL encode
- Valid examples:

`http%3A%2F%2Fapi.qrserver.com%2Fv1%2Fcreate-qr-code%2F%3Fdata%3D12345`
(URL encoded, equates to http://api.qrserver.com/v1/create-qr-code/?data=12345 in clear text)
- Invalid examples:

www.example.com/qrcode.png (invalid QR code URL, protocol declaration like http:// is missing)

### Request
```json
{
  "type": "qrcode",
  "symbol": {
    "seq": 0, 
    "data": "12345",
    "error": null
    }
  }
}
```
