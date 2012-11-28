## gsmtpd

_gsmtpd_ is a Python library implementing SMTP and LMTP protocols. It is similar to standart smtpd but it's based on gevent instead of asyncore.

For LMTPServer `process_message` function can return `None` or a list of SMTP statuses for each recipient in the same order.

## Example

```python
class TestServer(SMTPServer):
def process_message(self, peer, mailfrom, rcpttos, data):
    print peer, mailfrom, rcpttos, len(data)

s = TestServer(("127.1", 4000))
s.serve_forever()
```

