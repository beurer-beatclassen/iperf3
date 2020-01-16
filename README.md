# iPerf Speed Test

## Start Server


```
# Start a container for iperf2 (port 5001) and another for iperf3 (port 5201)
# without a specific network as defined in docker-compose.override.yml
docker-compose -f docker-compose.yml up --detach

# Logs
docker logs -f iperf2
docker logs -f iperf3
```

## Run Client
```
docker-compose build             # build docker images locally
iperf_server=iperf.example.com"  # set target server

# Run iperf2
docker run --rm toastie89/iperf2 sh -c "iperf -c $iperf_server"

# Run iperf3
docker run --rm toastie89/iperf3 sh -c "iperf3 -c $iperf_server"

```


## References
  - https://iperf.fr/
