# Document API Sproxy V1
## Default values
  - **HOST_URL** URL API default = HTTP Type + IP + PORT + PATH . Example : `http://192.168.1.99:8000/api/v1/`
  - **proxy,port** The value associated with the proxy port you can enter: IP:PORT or PORT ,Example : `192.168.1.99:5555` or `5555`
  - **Resporn** When success `error_code = 0` , When error `error_code = 1`
## API Status Proxy , Port :
### GET one proxy status
- Method : `GET`
```
/status?proxy={ip:port}
```
- Example : http://192.168.1.99:8000/api/v1/status?proxy=192.168.1.99:5555
### GET all proxy status
```
/status?proxy=all
```
- Example : http://192.168.1.99:8000/api/v1/status?proxy=all
## API Renew/change/rotate public IP :
### Renew/change/rotate one proxy port
- Method : `GET`
```
/reset?proxy={ip:port}
```
- Example : http://192.168.1.99:8000/api/v1/reset?proxy=192.168.1.99:5555
### Renew/change/rotate all proxy port
```
/reset_all
```
- Example : http://192.168.1.99:8000/api/v1/reset_all
## Reboot USB by proxy , port :
### Reboot one USB
- Method : `GET`
```
/reboot_usb?proxy={ip:port}
```
- Example : http://192.168.1.99:8000/api/v1/reboot_usb?proxy=192.168.1.99:5555
### Reboot All USB
```
/reboot_usb?proxy=all
```
- Example : http://192.168.1.99:8000/api/v1/reboot_usb?proxy=all
## Send SMS
- Method : `GET`
* Please url encode message data
```
/send_sms?port={ip:port}&phone={number_phone}&message={sms_content}
```
- Example : http://192.168.1.99:8000/api/v1/send_sms?port=192.168.1.99:5555&phone=+84987654321&message=HelloSproxy
## Read SMS
- Method : `GET`
* Type:
  - Inbox : Type = `1` 
  - Outbox : Type = `2` 
  - Drafts : Type = `3`
* Every page have 20 rows
```
/read_sms?port={ip:port}&type={1|2|3}&page={number}
```
- Example : http://192.168.1.99:8000/api/v1/read_sms?port=192.168.1.99:5555&type=1&page=1
## Delete SMS
- Method : `GET`
* Index : `separated by commas`
```
/delete_sms?port={ip:port}&index={index,index2,index3...}
```
- Example : http://192.168.1.99:8000/api/v1/delete_sms?port=192.168.1.99:5555&index=4000,40001,4002
## Send USSD
- Method : `GET`
* Please url encode Cmd data
```
/send_ussd?port={ip:port}&cmd={command}
```
- Example : http://192.168.1.99:8000/api/v1/send_ussd?port=192.168.1.99:5555&cmd=%2A101%23
## GET Resporn USSD by Port
- Method : `GET`
```
/get_ussd?port={ip:port}
```
- Example : http://192.168.1.99:8000/api/v1/get_ussd?port=192.168.1.99:5555
## GET ALL Resporn USSD
- Method : `GET`
```
/get_ussd?port=all
```
- Example : http://192.168.1.99:8000/api/v1/get_ussd?port=all