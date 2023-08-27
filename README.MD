# Research task

## Options to check deeper

### 1. [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/) with Terraform Integration

#### Pros:

- Managed service, so less overhead for the team.
- Direct integration with Terraform.
- Fine-grained access control using AWS IAM.

#### Cons:

- Costs associated with AWS Secrets Manager.
- If AWS is down (very rare), you might face access issues.

### 2. Kubernetes Native Secrets with [KMS](https://aws.amazon.com/kms/) Encryption

#### Pros:

- Uses native Kubernetes constructs.
- No additional costs other than KMS key usage.

#### Cons:

- Secrets in Kubernetes are base64 encoded, not encrypted. However, with KMS integration, they are encrypted at rest.
- Requires proper RBAC setup to ensure that secrets are not exposed to unauthorized pods.

### 3. [AWS Systems Manager](https://aws.amazon.com/systems-manager/) [Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)

#### Pros:

- Managed service with no additional cost for standard usage.
- Direct integration with Terraform.
- Fine-grained access control using AWS IAM.

#### Cons:

- Advanced features (like higher throughput) come with additional costs.
- If AWS is down (very rare), you might face access issues.

### 4. [Sealed Secrets](https://github.com/bitnami-labs/sealed-secrets)

#### Pros:

- Allows secrets to be stored in Git in an encrypted form.
- No need for an external service or store.

#### Cons:

- If you lose the encryption key (used by the controller), you lose access to the secrets.
- Rotation of secrets requires a bit more manual intervention.

---

There are other alternatives, but I need to start from these, as they are suit this task better.