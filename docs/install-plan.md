# DRAFT installation plan (not executed)

1. Confirm the [public infrastructure draft](https://github.com/newdarwindev/dots-local-sidecar-cloud-infrastructure) inventory gates: stable Linux host, backups, cluster placement, network and storage. Select pinned versions and test OpenBao/ESO integration in a disposable environment.
2. Establish private desired-state Git and restricted Argo CD AppProjects, source repositories and destinations. Argo CD owns deployments only. Install Argo Workflows separately for finite experiment jobs, with namespace/service-account isolation, quotas, TTL and artifact storage.
3. Add Keycloak OIDC for human UI login, mapping groups to service RBAC. Configure API authorization separately. Homepage may link to JupyterHub, Argo Workflows, Grafana and Langfuse but grants no access.
4. Offer JupyterHub/KubeSpawner with per-user persistent storage only after storage backup and quota policies are tested. BinderHub is optional for disposable demos and should receive no private datasets or secrets. Defer Kubeflow unless its complexity is justified by multiple workflows/teams.
5. Add Prometheus/Grafana/Loki for cluster health and logs. Add Langfuse for redacted LLM traces, prompt versions and evals. Specify data retention, access policy and redaction before any real trace ingestion.
6. Wire the gateway, typed validation, immutable dataset registry, DSPy worker and held-out evaluator. Start with synthetic offline inputs and no model endpoint. Test denial and failure paths before a separately approved real pilot.
7. Establish OpenBao policies and ESO stores per cluster; verify rotation, revocation and recovery. Keep bootstrap credentials and backups owner controlled and off-cluster. Do not put secrets in Git, traces, Slack, or notebooks.
8. Measure concurrency, CPU/memory/storage, model call and token ceilings, egress and GPU feasibility. Add cloud or GPU capacity only after budget and hardware validation.
