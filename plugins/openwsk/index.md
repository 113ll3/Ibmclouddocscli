---

copyright:

  years: 2016, 2017

lastupdated: "2017-01-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# OpenWhisk plug-in for Bluemix CLI
{: #openwsk_cli}

Use the OpenWhisk command line interface (CLI) to configure and manage OpenWhisk services. The OpenWhisk CLI plug-in is available for use with the Bluemix CLI plug-in.

The OpenWhisk CLI plug-in is available for Windows, MAC, and Linux operating systems. Ensure that you use the plug-in that is applicable to you.


To get started, install the IBM Bluemix CLI. See
[Bluemix CLI](docs/cli/reference/bluemix_cli/index.html) for details.

## Install the OpenWhisk CLI plug-in

**Note**: If you have a previous version of the plug-in that is installed, you need to uninstall it. Use the following command to uninstall the plug-in:

```
bluemix plugin uninstall openwhisk
```
### Install locally
Download the OpenWhisk plug-in for your platform from [IBM Bluemix CLI plug-in repository ![External link icon](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window}.

Install the OpenWhisk plug-in by using the following command:

**Note**: Either switch to the location of the plug-in or specify the path to the plug-in location.

* For Microsoft Windows OS:

```
bluemix plugin install openwhisk-win-amd64-0.1.0.exe
```

* For Apple MAC OS:

```
bluemix plugin install openwhisk-darwin-amd64-0.1.0
```

* For Linux OS:

```
bluemix plugin install openwhisk-linux-amd64
```

**Note**: While you are installing the plug-in for Linux OS, if you see an error message that shows permission is denied, then run the following command and change the permissions:

```
chmod a+x ./openwhisk-linux-amd64
```

### Install from Bluemix repository

Follow these steps to install the plug-in from the Bluemix repository:

1. Add the Bluemix plug-in registry endpoint:
	```
	bluemix plugin repo-add bluemix-bx http://plugins.stage1.ng.bluemix.net
	```

2. Run the following command:

	```
	bluemix plugin install openwhisk -r bluemix-bx
	```

## List of openwhisk commands
The following commands are supported. Use the `bluemix wsk` command to see the list of available commands:

<table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 1. General OpenWhisk commands</caption>
 <thead>
 <th colspan="6">General OpenWhisk commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk api](/docs/cli/plugins/openwsk/index.html#wsk_api)</td>
 <td>[bluemix wsk help](/docs/cli/plugins/openwsk/index.html#wsk_help)</td>
 <td>[bluemix wsk auth-key](/docs/cli/plugins/openwsk/index.html#wsk_auth_key)</td>
 <td>[bluemix wsk namespaces](/docs/cli/plugins/openwsk/index.html#wsk_namespaces)</td>
 <td>[bluemix wsk namespace](/docs/cli/plugins/openwsk/index.html#wsk_namespace)</td>
 <td>[bluemix wsk sdk-install](/docs/cli/plugins/openwsk/index.html#wsk_sdk_install)</td>
 </tr>
   </tbody>
 </table>

 <table summary="Alphabetically ordered Openwhisk action commands that have links that bring you to more info for the command">
<caption>Table 2. OpenWhisk action commands</caption>
 <thead>
 <th colspan="6">OpenWhisk action commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk actions](/docs/cli/plugins/openwsk/index.html#wsk_actions)</td>
 <td>[bluemix wsk action-create](/docs/cli/plugins/openwsk/index.html#wsk_action_create)</td>
 <td>[bluemix wsk action-update](/docs/cli/plugins/openwsk/index.html#wsk_action_update)</td>
 <td>[bluemix wsk action-delete](/docs/cli/plugins/openwsk/index.html#wsk_action_delete)</td>
 <td>[bluemix wsk action-invoke](/docs/cli/plugins/openwsk/index.html#wsk_action_invoke)</td>
 </tr>
   </tbody>
 </table>

 <table summary="Alphabetically ordered Openwhisk activation commands that have links that bring you to more info for the command">
<caption>Table 3. OpenWhisk activation commands</caption>
 <thead>
 <th colspan="6">OpenWhisk activation commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk activations](/docs/cli/plugins/openwsk/index.html#wsk_activations)</td>
 <td>[bluemix wsk activation](/docs/cli/plugins/openwsk/index.html#wsk_activation)</td>
 <td>[bluemix wsk activation-logs](/docs/cli/plugins/openwsk/index.html#wsk_activation_logs)</td>
 <td>[bluemix wsk activation-result](/docs/cli/plugins/openwsk/index.html#wsk_activation_result)</td>
 <td>[bluemix wsk activation-poll](/docs/cli/plugins/openwsk/index.html#wsk_activation_poll)</td>
 </tr>
   </tbody>
 </table>

 <table summary="Alphabetically ordered Openwhisk packages commands that have links that bring you to more info for the command">
<caption>Table 4. OpenWhisk packages commands</caption>
 <thead>
 <th colspan="6">OpenWhisk packages commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk packages](/docs/cli/plugins/openwsk/index.html#wsk_packages)</td>
 <td>[bluemix wsk package](/docs/cli/plugins/openwsk/index.html#wsk_package)</td>
 <td>[bluemix wsk package-create](/docs/cli/plugins/openwsk/index.html#wsk_package_create)</td>
 <td>[bluemix wsk package-update](/docs/cli/plugins/openwsk/index.html#wsk_package_update)</td>
 <td>[bluemix wsk package-delete](/docs/cli/plugins/openwsk/index.html#wsk_package_delete)</td>
 </tr>
 <tr>
 <td>[bluemix wsk package-bind](/docs/cli/plugins/openwsk/index.html#wsk_package_bind)</td>
 <td>[bluemix wsk package-refresh](/docs/cli/plugins/openwsk/index.html#wsk_pacakge_refresh)</td>
 </tr>
   </tbody>
 </table>

<table summary="Alphabetically ordered Openwhisk triggers commands that have links that bring you to more info for the command">
<caption>Table 5. OpenWhisk triggers commands</caption>
 <thead>
 <th colspan="6">OpenWhisk triggers commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk triggers](/docs/cli/plugins/openwsk/index.html#wsk_triggers)</td>
 <td>[bluemix wsk trigger](/docs/cli/plugins/openwsk/index.html#wsk_trigger)</td>
 <td>[bluemix wsk trigger-create](/docs/cli/plugins/openwsk/index.html#wsk_trigger_create)</td>
 <td>[bluemix wsk trigger-update](/docs/cli/plugins/openwsk/index.html#wsk_trigger_update)</td>
 <td>[bluemix wsk trigger-delete](/docs/cli/plugins/openwsk/index.html#wsk_trigger_delete)</td>
 <td>[bluemix wsk trigger-fire](/docs/cli/plugins/openwsk/index.html#wsk_trigger_fire)</td>
 </tr>
   </tbody>
 </table>

<table summary="Alphabetically ordered Openwhisk rules commands that have links that bring you to more info for the command">
<caption>Table 6. OpenWhisk rules commands</caption>
 <thead>
 <th colspan="6">OpenWhisk rules commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix wsk rules](/docs/cli/plugins/openwsk/index.html#wsk_rules)</td>
 <td>[bluemix wsk rule](/docs/cli/plugins/openwsk/index.html#wsk_rule)</td>
 <td>[bluemix wsk rule-create](/docs/cli/plugins/openwsk/index.html#wsk_rule_create)</td>
 <td>[bluemix wsk rule-update](/docs/cli/plugins/openwsk/index.html#wsk_rule_update)</td>
 <td>[bluemix wsk rule-enable](/docs/cli/plugins/openwsk/index.html#wsk_rule_enable)</td>
 <td>[bluemix wsk rule-disable](/docs/cli/plugins/openwsk/index.html#wsk_rule_disable)</td>
 </tr>
 <tr>
 <td>[bluemix wsk rule-status](/docs/cli/plugins/openwsk/index.html#wsk_rule_status)</td>
 <td>[bluemix wsk rule-delete](/docs/cli/plugins/openwsk/index.html#wsk_rule_delete)</td>
 </tr>
   </tbody>
 </table>

**Note:** To view help information for the commands, run the `bluemix wsk [command] -h` command.

### bluemix wsk api
{: #wsk_api}

View or set the API endpoint of OpenWhisk.

```
bluemix wsk api [HOST]
```

<strong>Command options</strong>:
   <dl>
   <dt>--skip-ssl-validation</dt>
   <dd>Allow insecure SSL certificate.</dd>
   <dt>--api-version</dt>
   <dd>Set API version.</dd>
    </dl>

### bluemix wsk help
{: #wsk_help}

View help information for all commands to operate OpenWhisk service.

```
bluemix wsk help
```

### bluemix wsk auth-key
{: #wsk_auth_key}

View or set the authentication key.

```
bluemix wsk auth-key [KEY]
```

### bluemix wsk namespaces
{: #wsk_namespaces}

List all namespaces.

```
bluemix wsk namespaces
```

### bluemix wsk namespace
{: #wsk_namespace}

List details of the specified namespace.

```
bluemix wsk namespace NAME
```

### bluemix wsk sdk-install
{: #wsk_sdk_install}

Install SDK artifacts. Valid COMPONENT is docker, and ios.

```
bluemix wsk sdk-install COMPONENT
```

### bluemix wsk actions
{: #wsk_actions}

List all actions under the specified namespace.

```
bluemix wsk actions NAMESPACE
```

<strong>Command options</strong>:
   <dl>
   <dt>--limit, -l</dt>
   <dd>Only return LIMIT number of actions from the collection (default 30).</dd>
   <dt>--skip, -s</dt>
   <dd>Exclude the first SKIP number of actions from the result.</dd>
    </dl>

### bluemix wsk action-create
{: #wsk_action_create}

Create an action.

```
bluemix wsk action-create NAMESPACE ACTION_NAME ACTION [-a, --annotation KEY,VALUE] [--copy] [--docker] [--kind KIND] [-l, --logsize LIMIT] [-m, --memory LIMIT] [-p, --param KEY,VALUE] [--sequence] [--shared] [-t, --timeout LIMIT]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--copy</dt>
   <dd>Treat ACTION as the name of an existing action.</dd>
   <dt>--docker</dt>
   <dd>Treat ACTION as docker image path on dockerhub.</dd>
   <dt>--kind</dt>
   <dd>The KIND of the action runtime (example: swift:3, nodejs:6).</dd>
   <dt>--logsize, -l</dt>
   <dd>The log size LIMIT in MB of the container that runs the action (default 10MB) (default -1).</dd>
   <dt>--memory, -m</dt>
   <dd>The memory LIMIT in MB of the container that runs the action (default -1).</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--sequence</dt>
   <dd>Treat ACTION as comma separated sequence of actions to invoke.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
   <dt>--timeout, -t</dt>
   <dd>The timeout LIMIT in milliseconds when the action will be terminated (default -1).</dd>
   </dl>

### bluemix wsk action-update
{: #wsk_action_update}

Update an existing action.

```
bluemix wsk action-update NAMESPACE ACTION_NAME ACTION [-a, --annotation KEY,VALUE] [--copy] [--docker] [--kind KIND] [-l, --logsize LIMIT] [-m, --memory LIMIT] [-p, --param KEY,VALUE] [--sequence] [--shared] [-t, --timeout LIMIT]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--copy</dt>
   <dd>Treat ACTION as the name of an existing action.</dd>
   <dt>--docker</dt>
   <dd>Treat ACTION as docker image path on dockerhub.</dd>
   <dt>--kind</dt>
   <dd>The KIND of the action runtime (example: swift:3, nodejs:6).</dd>
   <dt>--logsize, -l</dt>
   <dd>The log size LIMIT in MB of the container that runs the action (default 10MB) (default -1).</dd>
   <dt>--memory, -m</dt>
   <dd>The memory LIMIT in MB of the container that runs the action (default -1).</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--sequence</dt>
   <dd>Treat ACTION as comma separated sequence of actions to invoke.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
   <dt>--timeout, -t</dt>
   <dd>The timeout LIMIT in milliseconds when the action will be terminated (default -1).</dd>
   </dl>

### bluemix wsk action-delete
{: #wsk_action_delete}

Delete an action.

```
bluemix wsk action-delete NAMESPACE NAME
```

### bluemix wsk action-invoke
{: #wsk_action_invoke}

Invoke an action.

```
bluemix wsk action-invoke NAMESPACE NAME [-b, --blocking] [-r, --result] [-p, --param KEY,VALUE]
```

<strong>Command options</strong>:
   <dl>
   <dt>--block, -b</dt>
   <dd>Blocking invoke.</dd>
   <dt>-r, --result</dt>
   <dd>Show only activation result if a blocking activation (unless there is a failure).</dd>
   <dt>-p, --param KEY,VALUE</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
    </dl>

### bluemix wsk activations
{: #wsk_activations}

List activations.

```
bluemix wsk activations [NAMESPACE] [-f, --full] [-l, --limit LIMIT] [--since SINCE] [-s, --skip SKIP] [--upto UPTO]
```

<strong>Command options</strong>:
   <dl>
   <dt>--full, -f</dt>
   <dd>Include full activation description.</dd>
   <dt>--limit, -l</dt>
   <dd>Only return LIMIT number of activations from the collection (default 30).</dd>
   <dt>--since</dt>
   <dd>Return activations with timestamps later than SINCE; measured in milliseconds since Th, 01, Jan 1970.</dd>
   <dt>--skip, -s</dt>
   <dd>Exclude the first SKIP number of activations from the result.</dd>
   <dt>--upto</dt>
   <dd>Return activations with timestamps earlier than UPTO; measured in milliseconds since Th, 01, Jan 1970.</dd>
    </dl>

### bluemix wsk activation
{: #wsk_activation}

Get details of an activation.

```
bluemix wsk activation ACTIVATION_ID [-s, --summary]
```

<strong>Command options</strong>:
   <dl>
   <dt>--summary, -s</dt>
   <dd>Summarize activation details.</dd>
   </dl>

### bluemix wsk activation-logs
{: #wsk_activation_logs}

Get logs of an activation.

```
bluemix wsk activation-logs ACTIVATION_ID
```

### bluemix wsk activation-result
{: #wsk_activation_result}

Get result of an activation.

```
bluemix wsk activation-result ACTIVATION_ID
```

### bluemix wsk activation-poll
{: #wsk_activation_poll}

Poll log messages of currently running activations.

```
bluemix wsk activation-poll [NAMESPACE] [-e, --exit SECONDS] [--since-days DAYS] [--since-hours HOURS] [--since-minutes MINUTES] [--since-seconds SECONDS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--exit, -e</dt>
   <dd>Stop polling after SECONDS seconds.</dd>
   <dt>--since-days</dt>
   <dd>Start polling for activations DAYS days ago.</dd>
   <dt>--since-hours</dt>
   <dd>Start polling for activations HOURS hours ago.</dd>
   <dt>--since-minutes</dt>
   <dd>Start polling for activations MINUTES minutes ago.</dd>
   <dt>--since-seconds</dt>
   <dd>Start polling for activations SECONDS seconds ago.</dd>
    </dl>

### bluemix wsk packages
{: #wsk_packages}

List packages.

```
bluemix wsk packages NAMESPACE [-l, --limit LIMIT] [-s, --skip SKIP] [--shared]
```

<strong>Command options</strong>:
   <dl>
   <dt>--limit, -l</dt>
   <dd>Only return LIMIT number of packages from the collection (default 30).</dd>
   <dt>--skip, -s</dt>
   <dd>Exclude the first SKIP number of packages from the result.</dd>
   <dt>--shared</dt>
   <dd>Include publicly shared entities in the result.</dd>
    </dl>

### bluemix wsk package
{: #wsk_package}

Get details of a package.

```
bluemix wsk package NAMESPACE NAME
```

### bluemix wsk package-create
{: #wsk_package_create}

Create a package.

```
bluemix wsk package-create NAMESPACE PACKAGE_NAME [-a, --annotation KEY,VALUE] [-p, --param KEY,VALUE] [--shared]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
    </dl>

### bluemix wsk package-update
{: #wsk_package_update}

Update a package.

```
bluemix wsk package-update NAMESPACE PACKAGE_NAME [-a, --annotation KEY,VALUE] [-p, --param KEY,VALUE] [--shared]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
    </dl>

### bluemix wsk package-delete
{: #wsk_package_delete}

Delete a package.

```
bluemix wsk package-delete NAMESPACE NAME
```

### bluemix wsk package-bind
{: #wsk_package_bind}

Bind parameters to a package.

```
bluemix wsk package-bind NAMESPACE PACKAGE_NAME BOUND_PACKAGE_NAME [-a, --annotation KEY,VALUE] [-p, --param KEY,VALUE]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
    </dl>

### bluemix wsk package-refresh
{: #wsk_pacakge_refresh}

Refresh package bindings.

```
bluemix wsk package-refresh NAMESPACE
```

### bluemix wsk triggers
{: #wsk_triggers}

List triggers.

```
bluemix wsk triggers NAMESPACE [-l, --limit LIMIT] [-s, --skip SKIP]
```

<strong>Command options</strong>:
   <dl>
   <dt>--limit, -l</dt>
   <dd>Only return LIMIT number of triggers from the collection (default 30).</dd>
   <dt>--skip, -s</dt>
   <dd>Exclude the first SKIP number of triggers from the result.</dd>
    </dl>

### bluemix wsk trigger
{: #wsk_trigger}

Get details of a triger.

```
bluemix wsk trigger NAMESPACE NAME
```

### bluemix wsk trigger-create
{: #wsk_trigger_create}

Create a trigger.

```
bluemix wsk trigger-create NAMESPACE NAME [-a, --annotation KEY,VALUE] [-p, --param KEY,VALUE] [-f, --feed ACTION_NAME] [--shared]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--feed, -f</dt>
   <dd>Trigger feed ACTION_NAME.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
    </dl>

### bluemix wsk trigger-update
{: #wsk_trigger_update}

Update a trigger.

```
bluemix wsk trigger-update NAMESPACE NAME [-a, --annotation KEY,VALUE] [-p, --param KEY,VALUE] [--shared]
```

<strong>Command options</strong>:
   <dl>
   <dt>--annotation, -a</dt>
   <dd>Annotation values in KEY,VALUE format.</dd>
   <dt>--param, -p</dt>
   <dd>Parameter values in KEY,VALUE format.</dd>
   <dt>--shared</dt>
   <dd>Action visibility, default is false.</dd>
    </dl>

### bluemix wsk trigger-delete
{: #wsk_trigger_delete}

Delete a trigger.

```
bluemix wsk trigger-delete NAMESPACE NAME
```

### bluemix wsk trigger-fire
{: #wsk_trigger_fire}

Fire a trigger.

```
bluemix wsk trigger-fire NAMESPACE NAME [-p, --payload PAYLOAD] [-f, --file FILE]
```

<strong>Command options</strong>:
   <dl>
   <dt>--payload, -p</dt>
   <dd>Payload to send. Exclusive to -f.</dd>
   <dt>--file, -f</dt>
   <dd>File which contains the payload. Exclusive to -p.</dd>
    </dl>

### bluemix wsk rules
{: #wsk_rules}

List rules.

```
bluemix wsk rules NAMESPACE [-l, --limit LIMIT] [-s, --skip SKIP]
```

<strong>Command options</strong>:
   <dl>
   <dt>--limit, -l</dt>
   <dd>Only return LIMIT number of triggers from the collection (default 30).</dd>
   <dt>--skip, -s</dt>
   <dd>Exclude the first SKIP number of triggers from the result.</dd>
   </dl>

### bluemix wsk rule
{: #wsk_rule}

Get details of a rule.

```
bluemix wsk rule NAMESPACE NAME
```

### bluemix wsk rule-create
{: #wsk_rule_create}

Create a rule.

```
bluemix wsk rule-create NAMESPACE NAME TRIGGER_NAME ACTION_NAME [--enable] [--shared]
```

<strong>Command options</strong>:
  <dl>
  <dt>--enable</dt>
  <dd>Automatically enable rule after creation.</dd>
  <dt>--shared</dt>
  <dd>Action visibility, default is false.</dd>
  </dl>

### bluemix wsk rule-update
{: #wsk_rule_update}

Update a rule.

```
bluemix wsk rule-update NAMESPACE NAME TRIGGER_NAME ACTION_NAME [--shared]
```

<strong>Command options</strong>:
  <dl>
  <dt>--shared</dt>
  <dd>Action visibility, default is false.</dd>
  </dl>

### bluemix wsk rule-enable
{: #wsk_rule_enable}

Enable a rule.

```
bluemix wsk rule-enalbe NAMESPACE NAME
```

### bluemix wsk rule-disable
{: #wsk_rule_disable}

Disable a rule.

```
bluemix wsk rule-disable NAMESPACE NAME
```

### bluemix wsk rule-status
{: #wsk_rule_status}

Get rule status.

```
bluemix wsk rule-status NAMESPACE NAME
```

### bluemix wsk rule-delete
{: #wsk_rule_delete}

Delete a rule.

```
bluemix wsk rule-delete NAMESPACE NAME [--disable]
```

<strong>Command options</strong>:
  <dl>
  <dt>--disable</dt>
  <dd>Automatically disable rule before deletion.</dd>
  </dl>
