

# ngrok

> 컴퓨터 포트를 외부로 열어주는 프로그램

1. `ngrok.eye`가 존재하는 위치에서

```bash
./ngrok http 5000	# 5000은 port 넘버
```

2. webhook.py에 다음과 같이 작성

```python
TOKEN = '1757177605:AAF0hRsofqyOgj4LceR87AIrvxVtsFg_TqE'
APP_URL = f'https://api.telegram.org/bot{TOKEN}'
server_url = 'https://63f9c43177ba.ngrok.io'
webhook_url = f'{APP_URL}/setWebhook?url={server_url}'
print(webhook_url)
```

```bash
python webhook.py
```

3. print된 url 실행
4. 새로운 bash 창에서

```bash
flask run