---
layout: default
title: Helm
permalink: installation/kubernetes/helm
type: installation
category: kubernetes
redirect_from:
- installation/platforms/helm
display-title: "false"
language: en
list: include
abstract: Install Meshery on Kubernetes using Helm. Deploy Meshery in Kubernetes in-cluster.
---
# Install Meshery on Kubernetes Using Helm

<div class="prereqs"><h4>Prerequisites</h4>
<ol>
<li><a href="https://helm.sh/docs/intro/install/" class="meshery-light">Helm</a> should be installed on your local machine.</li>
<li>You should have access to the cluster/platform where you want to deploy Meshery.</li>
<li>Ensure that the kubeconfig file has the correct current context/cluster configuration.</li>
</ol>
</div>

## Install Meshery on Your Kubernetes Cluster Using Helm

{% capture code_content %}helm repo add meshery https://meshery.io/charts/
helm install meshery meshery/meshery --namespace meshery --create-namespace
{% endcapture %}
{% include code.html code=code_content %}

Optionally, Meshery Server supports customizing the callback URL for your remote provider, like so:

{% capture code_content %}helm install meshery meshery/meshery --namespace meshery --set env.MESHERY_SERVER_CALLBACK_URL=https://custom-host --create-namespace{% endcapture %}
{% include code.html code=code_content %}

### Customizing Meshery's Installation with values.yaml

Meshery's Helm chart supports a number of configuration options. Please refer to the [Meshery Helm chart](https://github.com/meshery/meshery/tree/master/install/kubernetes/helm/meshery#readme) and [Meshery Operator Helm Chart](https://github.com/meshery/meshery/tree/master/install/kubernetes/helm/meshery-operator#readme) for more information.

## Post-Installation Steps

Optionally, you can verify the health of your Meshery deployment, using <a href='/reference/mesheryctl/system/check'>mesheryctl system check</a>.

You're ready to use Meshery! Open your browser and navigate to the Meshery UI.

{% include_cached installation/accessing-meshery-ui.md %}

{% include related-discussions.html tag="meshery" %}
