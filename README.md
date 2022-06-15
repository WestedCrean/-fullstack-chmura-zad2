# Programowanie full-stack w chmurach obliczeniowych - Zadanie 2

Autor: Wiktor Flis <wiktor.flis@pollub.edu.pl>

W pliku `.github/workflows/main.yml` znajduje się pipeline z punktu 1 - uruchamiający testy a potem pakujący i wysyłający plik zip na EBS dostępny pod adresem http://docker-arm-env.eba-2gbpwe3f.us-east-1.elasticbeanstalk.com/

W pliku `.github/workflows/main.yml` znajduje się pipeline z punktu 2 - testuje aplikację jak w punkcie 1, ale tworzy za pomocą qemu obrazy na platformy linux/amd64,linux/arm64/v8,linux/arm/v7 i wysyła go do Docker Hub - a następnie przesyła sam spakowany docker-compose.yml do EBS aby uruchomić nowy deploy.
W definicji pipeline włączyłem w ostatnim kroku również parametr `wait_for_deployment: false` aby zaoszczędzić minuty darmowego czasu GitHub Actions.
Link do obrazu w Docker Hub: https://hub.docker.com/repository/docker/catherinium/react-app