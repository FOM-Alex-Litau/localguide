# Localguide - Ngix
Exemplarische Konfiguration des Reverse Proxys [nginx.conf](nginx.conf)</br>
</br>

Diese Konfiguration wurde für den Demobetrieb aufgebaut und ist natürlich veränderbar.
</br>
Es muss nur bedacht werden, dass die jeweiligen Applikationsbestandteile die URL aktualisieren müssen

Ngix stellt hierbei nur Routen bereit. Die jeweiligen anfragen Urls-Bestandteile werden rangehängt.

## Localguide - Ngix - Routen

| Technologie               | Listen-Url    | Destination-Url |
| :---:                     | :---: |:---: |
| **Plattform**    | https://litau.myqnapcloud.com:7000/*   |https://litau.myqnapcloud.com:7000/*  |
| **IAM (Keycloak)**        | https://litau.myqnapcloud.com:7000/realms/* <br/> https://litau.myqnapcloud.com:7000/resources/6q47a/* |  http://localguide.local:9009/realms/*  <br/> http://localguide.local:9009/resources/6q47a/* |
| **Backend (FastAPI)**    | https://litau.myqnapcloud.com:7000/localguide/api/*   | http://localguide.local:8000/* |
| **Frontend (Angular)**    | https://litau.myqnapcloud.com:7000/*   | http://localguide.local:4200/* |
