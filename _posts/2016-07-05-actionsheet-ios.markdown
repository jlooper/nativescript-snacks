---
layout: post
title:  "Implement iOS native ActionSheet"
date:   2016-07-05
categories: snippets
image: /images/popup.png
author: Dinh Le
tags: 
    - iOS
    - UIActionSheet
    - UIAlertController
shortdesc: 	How to implement the iOS native ActionSheet (with a 'cancel' button)
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/popup.png">
    </div>
  </li>


  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>

//Create AlertController
var alertController = UIAlertController.alertControllerWithTitleMessagePreferredStyle(null, null, UIAlertControllerStyle.UIAlertControllerStyleActionSheet);

//Declare actions that you want users to respond
var editAction = UIAlertAction.actionWithTitleStyleHandler(_("Edit"), UIAlertActionStyle.UIAlertActionStyleDefault, (arg: UIAlertAction) => {
  // implement your callback here
});
let deleteAction = UIAlertAction.actionWithTitleStyleHandler(_("Delete"), UIAlertActionStyle.UIAlertActionStyleDestructive, (arg: UIAlertAction) => {
  // implement your callback here
});
var cancelAction = UIAlertAction.actionWithTitleStyleHandler(_("Cancel"), UIAlertActionStyle.UIAlertActionStyleCancel, (arg: UIAlertAction) => {
  // implement your callback here
});

//Add actions to AlertController
alertController.addAction(editAction);
alertController.addAction(deleteAction);
alertController.addAction(cancelAction);

//Show the AlertController
var currentPage = topmost().currentPage;
var  viewController: UIViewController;
if (currentPage.modal) {
  viewController = currentPage.modal.ios;
} else {
  viewController = currentPage.ios;
}
viewController.presentModalViewControllerAnimated(alertController, true);		
		</code>
  </pre>
</div>
</li>

 
</ul>
