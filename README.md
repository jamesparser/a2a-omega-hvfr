# A2A Omega HVFR

**Hunt · Verify · Fix/Block · Report**

Hands-off multi-agent DevSecOps lifecycle automation built on [A2A Omega](https://github.com/jamesparser/a2a-omega).

**GitLab Transcend — Life After Code** (Oct 5–27, 2026) · Path B: Bring Your Own · Hands-off Agent

## Why HVFR

Writing the code is the easy part. HVFR keeps a multi-agent fleet busy on the *post-code* DevSecOps lifecycle with **no human in the middle**:

| Role | Jobs | GitLab stage | Does |
|---|---|---|---|
| **Hunter** | Hunt + Report | Secure | Scans MRs/commits for bugs & vulns; files findings |
| **Verifier** | Verify + Fix/Block | Verify | Independently confirms findings; fixes or blocks |
| **Triage** | Govern | Govern | Policy, vuln management, auto-close false positives |

## Hands-off by design

- Scheduled **hourly** tasks keep every agent hunting / verifying / fixing / reporting
- A2A agent-to-agent orchestration — hunter → independent verifier → resolution
- GitLab CI trigger on MR/commit events; agents operate on GitLab data (MRs, issues, pipelines)

## Upstream

Fork/adaptation of `jamesparser/a2a-omega` (A2A routing hub). Orchestration + verification handoff preserved; tasks re-pointed from external bounty hunting → GitLab post-code lifecycle automation.

## Layout

```
a2a_hub.py          # routing hub / multi-identity fleet
a2a_agentverse.py   # Agentverse transport
a2a_e2a.py          # e2a email transport
a2a_client.py       # client
poller.py           # scheduled poll / keep-busy loop
mesh_test.py        # mesh ping/pong test
config/peers.example.json
```
