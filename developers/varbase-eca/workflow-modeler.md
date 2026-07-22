# Building ECA Workflows With the Workflow Modeler

The **Workflow Modeler** is the default visual editor for **ECA** models in Varbase 11.0.x. It shows each model as a diagram of connected nodes, lets you configure each node in a side panel, and can replay a real run of the model step by step so you can check that it behaves as intended.

This guide walks through opening the editor, building a small model, and reviewing how it runs. For background on ECA and the list of models Varbase ships, see [Varbase ECA (Workflow Automation)](README.md).

## Opening the Workflow Modeler

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_ (`/admin/config/workflow/eca`). The models list shows every ECA model with its components, version, enabled state, and operations.

- To start a new model, select **Add New Model**.
- To open an existing model, select **Edit** on its row.

When the Workflow Modeler is the only visual editor installed, both actions open it directly. If more than one editor is installed (for example, the **BPMN.iO Modeler** as well), the operations menu offers a separate "Edit with" entry for each editor, and you choose the Workflow Modeler there.

## The Model Information Dialog

A new model opens with the **Model Information** dialog, where you set the basics:

- **Label**: the human-readable name shown in the models list.
- **Machine Name**: generated from the label, or set your own.
- **Version**: a free-text version string for the model.
- **Enabled**: whether the model runs.
- **Template**: whether the model is offered as a starting point for new models.
- **Documentation** and **Tags**: optional notes and labels.

![The Model Information dialog for a new ECA model](<../../.gitbook/assets/Workflow Modeler - Model Information.png>)

Select **Save** in the dialog to move on to the canvas.

## The Canvas

The canvas is where you build the model. Nodes are colour-coded by role:

- **Event** nodes start the workflow.
- **Condition** nodes gate what happens next.
- **Action** nodes carry out the work.

Each node has a quick-add **+** control on its connector; selecting it adds the next step. Selecting a node opens its **properties panel** on the right.

### Adding an Event

Select **New Event** to add the starting event, then choose the event from the list (for example, **Insert content entity** for "after new content is saved").

![An Insert content entity event on the canvas](<../../.gitbook/assets/Workflow Modeler - Event Properties.png>)

The properties panel shows the event's settings. For a content event you can set the **Type (and bundle)** so the workflow only reacts to a chosen content type, such as a blog post.

### Adding a Successor

Select the **+** control below a node to open the **Add Successor** panel. It lists the actions and conditions you can connect next, with a search box and a filter. Recommended entries appear first.

![The Add Successor panel listing available actions and conditions](<../../.gitbook/assets/Workflow Modeler - Add Successor.png>)

Pick an entry (for example, **Log Message**) to add it and connect it to the previous node.

### Configuring a Node

Select any node to configure it in the properties panel. Each field is described inline, and text fields are token-aware: you can insert placeholders such as `[entity:title]` or `[entity:nid]` that are replaced with real values when the workflow runs.

![An Action node with its properties panel, including a token-aware message field](<../../.gitbook/assets/Workflow Modeler - Action Configured.png>)

Select **Save** in the top bar to store the model. Saving writes the model's ECA configuration; the diagram layout is derived from that configuration.

## Reviewing a Flow

The Workflow Modeler can capture and replay a real execution of a saved model, which helps you confirm the workflow does what you expect.

On a saved model, select an event node, then select **Review Flow** in the properties panel.

![The Review Flow button on a saved model](<../../.gitbook/assets/Workflow Modeler - Review Flow Button.png>)

Once the model runs on the site (for example, you create a matching piece of content), the captured run appears with playback controls. You can step through the run, play it at **0.5×**, **1×**, **2×**, or **4×**, and inspect the **Step Data** and tokens available at each step.

![A captured execution replayed in Review Flow, with playback controls and step data](<../../.gitbook/assets/Workflow Modeler - Review Flow Execution.png>)

{% hint style="info" %}
**Review Flow** is specific to the Workflow Modeler. It replays a recorded run of the model, so you can see which nodes fired and what data they had, without reading logs.
{% endhint %}

## Opening Existing Models

An ECA model is stored as its `eca.eca.*` configuration entity, not as a saved drawing. The Workflow Modeler re-derives the diagram from that configuration and lays it out automatically each time you open the model.

Because of this, models authored earlier in the **BPMN.iO Modeler** open in the Workflow Modeler with no migration and no change to the stored configuration until you save. The pre-configured Varbase model **Redirect 403 to Login**, for example, opens as a clean event-condition-action diagram.

![The Redirect 403 to Login model rendered in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Redirect 403 to Login Model.png>)

## Pre-Configured Models

Varbase ships several ready-made ECA models that you can open and study in the Workflow Modeler. See the [pre-configured models list](README.md#pre-configured-eca-models-in-varbase) for the full set, including [Redirect 403 to Login](redirect-403-to-login.md), which the **Varbase Content Base** recipe ships.

## For QA

Use this checklist when reviewing the Workflow Modeler on a Varbase site:

- The ECA models list opens at `/admin/config/workflow/eca` and lists the pre-configured models.
- **Add New Model** opens the Workflow Modeler and the **Model Information** dialog.
- A new model can be built from an event, a successor action, and a saved configuration.
- **Edit** on an existing model opens it as a diagram with no errors.
- Pre-configured models (for example, **Redirect 403 to Login**) render as connected event, condition, and action nodes.
- **Review Flow** captures a run and plays it back with the step data.
