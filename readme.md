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
  ...
}
```
