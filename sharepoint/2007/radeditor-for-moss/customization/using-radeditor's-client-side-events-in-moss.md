---
title: Using RadEditor's Client-Side events in MOSS
page_title: Using RadEditor's Client-Side events in MOSS | UI for ASP.NET AJAX Documentation
description: Using RadEditor's Client-Side events in MOSS
slug: sharepoint/2007/radeditor-for-moss/customization/using-radeditor's-client-side-events-in-moss
tags: using,radeditor's,client-side,events,in,moss
published: True
position: 2
---

# Using RadEditor's Client-Side events in MOSS

Telerik RadEditor's provides a very rich Client-Side API which is very useful when implementing some more complicated scenarios. Bellow are the editor's Client-Side events:

* [OnClientLoad]({%slug editor/client-side-programming/events/onclientload%})

* [OnClientCommandExecuting]({%slug editor/client-side-programming/events/onclientcommandexecuting%})

* [OnClientCommandExecuted]({%slug editor/client-side-programming/events/onclientcommandexecuted%})

* [OnClientModeChange]({%slug editor/client-side-programming/events/onclientmodechange%})

* [OnClientPasteHtml]({%slug editor/client-side-programming/events/onclientpastehtml%})

* [OnClientSelectionChange]({%slug editor/client-side-programming/events/onclientselectionchange%})

* [OnClientSubmit]({%slug editor/client-side-programming/events/onclientsubmit%})



In order to execute you custom code called when RadEditor's Client-Side event is fired you need to:

1. Set the desired event in the respective ConfigFile

1. Put your custom code in the \wpresources\RadEditorSharePoint\5.x.x.x**1f131a624888eeed\Resources\ MOSSEditorTools.js

**For example:**

Open the **\wpresources\RadEditorSharePoint\5.x.x.x**1f131a624888eeed\Resources\**ConfigFile.xml** and attach the editor's OnClientLoad event to your custom OnClientLoad function e.g.

`<property name="**OnClientLoad**">OnClientLoad</property>`

Next, open the \wpresources\RadEditorSharePoint\5.x.x.x**1f131a624888eeed\Resources\**MOSSEditorTools.js** and set your custom **OnClientLoad**function e.g.

````JavaScript
function OnClientLoad(editor, args)
{
	editor.attachEventHandler("onkeydown", function (e)
	{
		alert("Content area key down " + e.keyCode);
	});
}
````

Clear the browser's cache and test what the result is.

For more information, about the editor's Client-Side API please review the Client-Side API Reference section of the [RadEditor for ASP.NET AJAX help]({%slug editor/overview%}).
