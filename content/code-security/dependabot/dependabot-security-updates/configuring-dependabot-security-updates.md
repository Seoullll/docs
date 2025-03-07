---
title: Configuring Dependabot security updates
intro: 'You can use {% data variables.product.prodname_dependabot_security_updates %} or manual pull requests to easily update vulnerable dependencies.'
shortTitle: Configure security updates
redirect_from:
  - /articles/configuring-automated-security-fixes
  - /github/managing-security-vulnerabilities/configuring-automated-security-fixes
  - /github/managing-security-vulnerabilities/configuring-automated-security-updates
  - /github/managing-security-vulnerabilities/configuring-github-dependabot-security-updates
  - /github/managing-security-vulnerabilities/configuring-dependabot-security-updates
  - /code-security/supply-chain-security/configuring-dependabot-security-updates
  - /code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/configuring-dependabot-security-updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>3.2'
type: how_to
topics:
  - Dependabot
  - Security updates
  - Alerts
  - Dependencies
  - Pull requests
  - Repositories
---
<!--Marketing-LINK: From home page "Learn more about Dependabot".-->

{% data reusables.dependabot.beta-security-and-version-updates %}
{% data reusables.dependabot.enterprise-enable-dependabot %}

## About configuring {% data variables.product.prodname_dependabot_security_updates %}

You can enable {% data variables.product.prodname_dependabot_security_updates %} for any repository that uses {% data variables.product.prodname_dependabot_alerts %} and the dependency graph. For more information, see "[About {% data variables.product.prodname_dependabot_security_updates %}](/github/managing-security-vulnerabilities/about-dependabot-security-updates)."

You can disable {% data variables.product.prodname_dependabot_security_updates %} for an individual repository or for all repositories owned by your user account or organization. For more information, see "[Managing {% data variables.product.prodname_dependabot_security_updates %} for your repositories](#managing-dependabot-security-updates-for-your-repositories)" below.

{% ifversion fpt or ghec %}{% data reusables.dependabot.dependabot-tos %}{% endif %}

## Supported repositories

{% data variables.product.prodname_dotcom %} automatically enables {% data variables.product.prodname_dependabot_security_updates %} for every repository that meets these prerequisites.

{% note %}

**Note**: You can manually enable {% data variables.product.prodname_dependabot_security_updates %}, even if the repository doesn't meet some of the prerequisites below. For example, you can enable {% data variables.product.prodname_dependabot_security_updates %} on a fork, or for a package manager that isn't directly supported by following the instructions in "[Managing {% data variables.product.prodname_dependabot_security_updates %} for your repositories](#managing-dependabot-security-updates-for-your-repositories)."

{% endnote %}

| Automatic enablement prerequisite | More information |
| ----------------- | ----------------------- |
| Repository is not a fork | "[About forks](/github/collaborating-with-issues-and-pull-requests/about-forks)" |
| Repository is not archived | "[Archiving repositories](/github/creating-cloning-and-archiving-repositories/archiving-repositories)" |{% ifversion fpt or ghec %}
| Repository is public, or repository is private and you have enabled read-only analysis by {% data variables.product.prodname_dotcom %}, dependency graph, and vulnerability alerts in the repository's settings | "[Managing data use settings for your private repository](/get-started/privacy-on-github/managing-data-use-settings-for-your-private-repository)." |{% endif %}
| Repository contains dependency manifest file from a package ecosystem that {% data variables.product.prodname_dotcom %} supports | "[Supported package ecosystems](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph#supported-package-ecosystems)" |
| {% data variables.product.prodname_dependabot_security_updates %} are not disabled for the repository | "[Managing {% data variables.product.prodname_dependabot_security_updates %} for your repository](#managing-dependabot-security-updates-for-your-repositories)" |

If security updates are not enabled for your repository and you don't know why, first try enabling them using the instructions given in the procedural sections below. If security updates are still not working, you can contact {% data variables.contact.contact_support %}.

## Managing {% data variables.product.prodname_dependabot_security_updates %} for your repositories

You can enable or disable {% data variables.product.prodname_dependabot_security_updates %} for an individual repository (see below).

You can also enable or disable {% data variables.product.prodname_dependabot_security_updates %} for all repositories owned by your user account or organization. For more information, see "[Managing security and analysis settings for your user account](/github/setting-up-and-managing-your-github-user-account/managing-security-and-analysis-settings-for-your-user-account)" or "[Managing security and analysis settings for your organization](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)."

{% data variables.product.prodname_dependabot_security_updates %} require specific repository settings. For more information, see "[Supported repositories](#supported-repositories)."

### Enabling or disabling {% data variables.product.prodname_dependabot_security_updates %} for an individual repository

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.navigate-to-code-security-and-analysis %}
1. Under "Code security and analysis", to the right of "{% data variables.product.prodname_dependabot %} security updates", click **Enable** to enable the feature or **Disable** to disable it. {% ifversion fpt or ghec %}For public repositories, the button is disabled if the feature is always enabled.{% endif %}
  {% ifversion fpt or ghec %}!["Code security and analysis" section with button to enable {% data variables.product.prodname_dependabot_security_updates %}](/assets/images/help/repository/enable-dependabot-security-updates-button.png){% else %}!["Code security and analysis" section with button to enable {% data variables.product.prodname_dependabot_security_updates %}](/assets/images/enterprise/3.3/repository/security-and-analysis-disable-or-enable-ghes.png){% endif %}


## Further reading

- "[About {% data variables.product.prodname_dependabot_alerts %}](/code-security/supply-chain-security/about-alerts-for-vulnerable-dependencies)"{% ifversion fpt or ghec %}
- "[Managing data use settings for your private repository](/get-started/privacy-on-github/managing-data-use-settings-for-your-private-repository)"{% endif %}
- "[Supported package ecosystems](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph#supported-package-ecosystems)"
