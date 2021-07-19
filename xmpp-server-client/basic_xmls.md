1. The very first thing we need to do after establishing a *TCP* connection with any XMPP server is to start a stream:
```xml
<?xml version='1.0'?> <stream:stream to='ckotha.com' xmlns='jabber:client' xmlns:stream='http://etherx.jabber.org/streams' version='1.0'>
```

2. Login:
```xml
<iq type='set' id='auth2'><query xmlns='jabber:iq:auth'><username>matin1</username><password>password</password><resource>jingle</resource></query></iq>
```
**alert**: It's always to risky to pass credentials in plain text, but we've done this for learning purpose only

3. Send a basic message:
```xml
<message to='matin2@ckotha.com'><subject>testing!</subject><body>hi from c++ client</body></message>
```
