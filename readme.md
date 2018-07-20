# Einfaches Besipiel eines Java-Skills.

Bauen mit: mvn assembly:assembly -DdescriptorId=jar-with-dependencies package

Handler: com.amazon.asksdk.helloworld.HelloWorldSpeechletRequestStreamHandler

Laufzeit: Java 8

Anmerkung:
Das Beispiel implementiert SpeechletV2:
```java
public class HelloWorldSpeechlet implements SpeechletV2;
```
es ist auch möcglich, Speechlet zu implementieren.
Die Signatur der Methode würde wie folgt aussehen:

```java
public class Hello implements Speechlet {
	@Override
	public void onSessionStarted(SessionStartedRequest request, Session session) throws SpeechletException {
		// TODO Auto-generated method stub
	}
  @Override
	public SpeechletResponse onIntent(final IntentRequest request, final Session session) throws SpeechletException {
		log.info("onIntent requestId={}, sessionId={}", request.getRequestId(), session.getSessionId());
		System.out.println("Session:"+session+ " Intent:"+request.getIntent().getName());
		String intentName = request.getIntent().getName();
		if (INTENT_ABC.equals(intentName)) {
			return handleAbc(request.getIntent(), session);
		} else if (INTENT_XYZ.equals(intentName)) {
			return handleXyz(session);
		} else if ("AMAZON.HelpIntent".equals(intentName)) {
			return handleHelpIntent();
		} else if ("AMAZON.StopIntent".equals(intentName)) {
			return handleStopIntent();
		} else {
			throw new SpeechletException("Invalid Intent");
		}
	}
}
```
