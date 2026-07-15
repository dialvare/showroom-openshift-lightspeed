---
title: APEX Cloud Platform API gateway certificate
url: "https://www.dell.com/support/manuals/es-es/apex-cloud-pf-rh-openshift/acp_rhos_ag/apex-cloud-platform-api-gateway-certificate?guid=guid-e887cf4b-346c-454d-a523-364d4145eeb1&lang=en-us"
---

# APEX Cloud Platform API gateway certificate

The APEX Cloud Platform plug-in consumes the ACP API gateway certificate.

You can view and update the APEX Cloud Platform API gateway certificate using the APEX Cloud Platform UI.

The default certificate is valid for two years from the creation date of the cluster.

The default certificate for the API gateway does not autorotate.

## Customer-supplied certificates

You can replace the certificate for the API gateway with a customer-supplied certificate with the following details:

The common name (CN) of the certificate subject should be:

```
api-gateway.dell-acp.apps.<cluster-name>.<cluster-domain>
```

The subject alternative name (SAN) of the certificate extension should contain the following two DNS type entries:

```
api-gateway.dell-acp.apps.<cluster-name>.<cluster-domain>
mcp-depot-storage-docker.dell-acp.apps.<cluster-name>.<cluster-domain>
```

If the certificate is a self-signed certificate, then the certificate should also include the Basic Constraints extension with the CA field set to `TRUE`. For example: `basicConstraints=CA:TRUE`

Updating the APEX Cloud Platform API gateway certificate may take one or more minutes.