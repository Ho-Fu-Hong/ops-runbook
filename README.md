# Ops Runbook

Notes for the night shift on the property systems API at
`ops-api.sandschina.com`.

## Check a stuck interface

If the PMS interface stops posting charges, check its queue first:

    curl -H "Authorization: Bearer SYNTHETIC-Jd83kQm2Xv71pLr9Tz46Wn05" https://ops-api.sandschina.com/v1/interfaces/pms/queue

Then restart the interface from the admin console and post a note in the shift log.

## Queue check script

    export OPS_API_TOKEN=SYNTHETIC-Ht5pW2mQ8zR1vK7xN4cB
    python tools/queue_check.py pms

## Escalation

Call the on-call engineer if the queue is above 500 after a restart.
