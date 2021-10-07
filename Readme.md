# Run the server 
`python3 server.py`



# Plot
```
echo 'GET https://google.com' | \
    vegeta attack -rate 100 -duration 2m | vegeta encode | tee result.bin | \
    jaggr @count=rps \
          hist\[100,200,300,400,500\]:code \
          p25,p50,p95:latency | \
    jplot code.hist.100+code.hist.200+code.hist.300+code.hist.400+code.hist.500 \
          && cat result.bin | vegeta report
```

# Branch
# v1
normal one

# v2
- Handle SIGTERM

# v3
- Edit Dockerfile `CMD python /server.py` -> `CMD ["python", "/server.py"]`

# v4
- Add Conneciton close header

# v5 
- Add Prestop hook