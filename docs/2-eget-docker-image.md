# Eget docker image

I [Hello World](1-hello-world.md) kapitlet, blev der brugt et offentlig tilgængelig docker image. I de fleste tilfælde vil man dog have brug for at bruge egne images i sit setup.

Der findes mange forskellige online image repositories. I dette eksempel vil jeg anvende github som eksempel. For at følge med, er det derfor nødvendigt at have en github konto med adgang til [Github Packages](https://docs.github.com/en/packages)

Start med at lave et lokalt docker-image:

```bash
$ docker build -t eget-docker-image \
        -f src/2-eget-docker-image/Dockerfile \
        ./src/2-eget-docker-image
```

Dette image skal så pushed til github - udskift `<github-user-name>` med eget brugernavn

```bash
$ docker tag eget-docker-image ghcr.io/<github-user-name>/eget-docker-image
$ docker push ghcr.io/<github-user-name>/eget-docker-image
```

Dette vil fejle, hvis der ikke er logget ind i docker med github. 

Følgende steps skal følges for at udføre dette:

1. Opret Access Token med rettighed til read, write og delete packages - [Følge denne guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
2. 