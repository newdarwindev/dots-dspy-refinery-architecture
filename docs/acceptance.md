# DRAFT acceptance checklist

- [ ] Slack signature, timestamp/replay, actor mapping, allowlist and rate-limit tests pass.
- [ ] Invalid/unknown fields and unpinned dataset, program, model or evaluation references are denied.
- [ ] Idempotent retries create no duplicate workflow; cancellation checks authorization.
- [ ] Workflow has scoped identity, quota, network policy, TTL and no deployment-Git write access.
- [ ] Optimizer never sees held-out labels; gold labels have human review and provenance.
- [ ] No automatic use of private Slack history for training or labeling.
- [ ] Manifest pins hashes, versions, metrics, trace and costs; failed/incomplete runs cannot promote.
- [ ] Owner reviews exact candidate, baseline, regression and privacy report before promotion PR.
- [ ] Branch protection and Argo CD AppProject restrict Git source and destination.
- [ ] Keycloak UI sign-in and API authorization are separately tested; Homepage does not bypass either.
- [ ] OpenBao/ESO rotation, revocation and restore pass in each destination cluster.
- [ ] Persistent JupyterHub data has quota and backup; BinderHub demo contains no private data.
- [ ] Infra metrics/logs and redacted LLM traces have distinct retention and access policies.
- [ ] Pilot budget, concurrency, runtime, storage and model token ceilings are approved.
- [ ] Rollback to prior pinned artifact succeeds in a disposable environment.

None of these operational checks are asserted as complete by this documentation repository.
