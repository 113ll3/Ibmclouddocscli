---



copyright:

  years: 2016, 2017

lastupdated: "2017-01-12"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}



<!-- This template is for introducing a command line interface(cli). It is a conceptual template intended to document productive use of the cli. It is not intended for task information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->


# <CLI_name> commands
<!-- Insert your CLI name into topic title above. -->
<!-- The navigation title should be just <CLI_name>. -->
{: #CLI_name}
<!-- Provide an appropriate ID above -->


<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use this cli. This should be conversational style. For search engine optimization, include cli name. Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Example: -->

The Bluemix command line interface, which is called cloud-cli, provides extra capabilities for service offerings. You can use cloud-cli to manage V2 service brokers and templates.
{:shortdesc}


<!-- Prerequisites/Authorization/Environment: OPTIONAL
The section should lists all the prerequisites/authorization/environment that are required to use the cli commands. Or give a brief introduction to the prerequisites/authorization/environment that the cli commands might use. Use **Note** to call out this section.
Examples: -->

**Note**: cloud-cli requires Java 1.7.0. You can download cloud-cli from Bluemix to use on your local system as a complement to the Bluemix user interface.


<!-- Commands index: REQUIRED
Use a table to list out all the commands so that commands information is easy to scan and locate. Add a link to the anchor of each command.
Use "<CLI_name> commands index" as section title.
If there are a great many commands, to make it easy to retrieve specific commands, you can add several index tables. Group the commands by functions or other similar characteristics, and then make one group a table.
  - Arrange the commands in alphabetical order,across columns, then rows.
  - To look neat and clean, include no more than 5 columns for a table.
Example: -->


## <CLI_name> commands index
{: #CLIname_commands_index}

Use the index in the following table to refer to the frequently used <CLI_name> commands:

<table summary="Alphabetically ordered commands that belong to group A and each command has a link that brings you to more info for the command">
 <thead>
 <th colspan="3">Group A commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[cmda](link_to_cmda)</td>
 <td>[cmdb](link_to_cmdb)</td>
 <td>[cmdc](link_to_cmdc)</td>
 </tr>
 <tr>
 <td>[...](...)</td>
 <td>[...](...)</td>
 <td>[...](...)</td>
 </tr>
  </tbody>
 </table>
{: caption="Table 1. Group A commands" caption-side="top"}


<table summary="Alphabetically ordered commands that belong to group B and each command has a link that brings you to more info for the command">
 <thead>
 <th colspan="3">Group B commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[cmd1](link_to_cmd1)</td>
 <td>[cmd2](link_to_cmd2)</td>
 <td>[cmd3](link_to_cmd3)</td>
 </tr>
 <tr>
 <td>[...](...)</td>
 <td>[...](...)</td>
 <td>[...](...)</td>
 </tr>
 </tbody>
 </table>
{: caption="Table 2. Group B commands" caption-side="top"}

<!-- Command entries: REQUIRED
Directly use the command as title.  Add an anchor ID, for example, {: #login}, for each command entry, so that you can link to the command entry from the index table.
Include a sentence to briefly introduce the command. Such as what does this command do.
The following items are OPTIONAL. Include as many items as needed.

Command syntax: Add the command syntax by using three backticks ahead of and after the syntax (```).

Command prerequisites/authorization/environment: Prerequisites/authorization/environment that are required to use this command. Use the <strong></strong> html markup to highlight the word prerequisites/authorization/environment.

Command Options: Use the <strong></strong> html markup to highlight the word "Command options".
                 Use a definition list to introduce the options. Make one option one list item.

Examples: Use the <strong></strong> html markup to highlight the word "Examples".
          - Include one sentence to describe each example.
		  - Add the example by using three backticks ahead of and after the example (```)
		  - For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
		  - For non-copyable output snippet, include {: screen} following the last set of backticks.
                  - For copyable command, single line, include {: codeblock} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include                     just the command example.

Example: -->

## login
{: #login}

Use this command to log in to Bluemix.

```
cloud-cli login [userID] [pw]
```

<strong>Prerequisites</strong>: None.

<strong>Command options</strong>:

   <dl>
   <dt>userID</dt>
   <dd>The Bluemix user ID.</dd>
   <dt>pw</dt>
   <dd>The user's password for Bluemix.</dd>
    </dl>

<strong>Examples</strong>:

Log in to Bluemix with the userID *Tom* and password *p123*.
```
cloud-cli login Tom p123
```
{: codeblock}




## command xxx
{: #command_xxx}

...


<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page.
Ensure that you retain the lowercase anchor IDs (eg. {: #rellinks}) as shown in this template. These are used as IDs during transform and the doc framework keys off the IDs for display.
The headings coded here are not actually used. The doc framework provides the correct headings.
Also ensure that the related links stay in position at the end of this file or the doc framework will not display them properly.
Use {:new_window} for external links to open a new window. And, use ![External link icon](../icons/launch-glyph.svg) at the end of the link text to include the external link icon.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->

# Related Links
{: #rellinks}

## Related Links
{: #general}

<!-- Include a link to download your command line tool, and the link to your full product documentation, pricing sheet, IBM Bluemix prerequisites -->


* [link text](URL){:new_window}
* [link text](URL){:new_window}
