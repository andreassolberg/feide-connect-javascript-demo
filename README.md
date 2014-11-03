
# Feide Connect Javascript klient


Dette er eksempelkode i Javascript for uthenting av eksamensresultater fra FS via Feide Connect.

*Denne koden skal kun brukes for ekperimentering og opplæring.*

Vi anbefaler at du gjør følgende:

1. Installerer og setter opp denne applikasjonen og får den til å fungere mot Feide Connect.
2. Tar en titt på koden

Du kan også 

* [Teste vår ferdig installerte og konfigurerte versjon av den samme appen](http://eksamen.andreas.uninettlabs.no/webapp/) for å sammenligne hvordan det skal fungere.


## Installer og konfigurer denne demo appen

Drop filene inn på en webtjener (f.eks. Apache) som kan levere statiske filer.

Merk deg nettadressen index.html vil bli eksponert på, denne URL-en skal registreres som `redirect_uri` når klienten registreres hos Feide Conncet.

Da er tiden inne for å registrere klienten på Feide Connect. Følg lenken til [Feide Connect Developer dashboard](https://dev.uwap.uninettlabs.no), og velg *Register new client*.

Fyll inn navn og beskrivelse og lim inn Redirect URI-en du tidligere noterte deg.

![](http://clippings.erlang.no/ZZ6FFAC34F.jpg)

Finn eksamensresultater API og be om tilgang til dette.

![](http://clippings.erlang.no/ZZ3B2895F9.jpg)

Verifiser senere at du har blitt tildelt tilgang:

![](http://clippings.erlang.no/ZZ79F2F272.jpg)


Nå skal du fylle inn tildelt `client_id` og `redirect_uri`-en som du både noterte deg tidligere og registrerte hos Feide conncet, inn i konfigurasjonen i filen `js/main-dev.js`:

```javascript
	this.jso = new JSO({
		providerId: "feideconnect",
		client_id: "___fill_in___",
		redirect_uri: "___fill_in___",
		authorization: "https://auth.uwap.uninettlabs.no/oauth/authorization"
	});
```

Etter å ha konfigurert ferdig, kan du gå til applikasjonens URL, og du vil så bli sendt til Feide Connect for pålogging og godkjenning.


Først får man valg om hvor man vil logg inn med. Dersom man ønsker å logge inn med Feide sin testbruker så velger man *Feide*.

Deretter logger man inn med testbrukernavn og passord (spør Andreas).

![](http://clippings.erlang.no/ZZ3EEF9417.jpg)

Man vil så som sluttbruker bekrefte at man ønsker å gi tilgang til at klienten henter ut eksamensresultater og brukerinformasjon:

![](http://clippings.erlang.no/ZZ181480E7.jpg)

Når appen klarer å hente ut eksamensresultater er man i mål! Gratulerer!






