Sometimes the answer to your problem is where it is supposed to be : in the documentation and not Stackoverflow... I had an issue the other day to make the backButton work for the navigationBar but when reading the doc everything is clear:

**You're doing it wrong!**

> Updating the Navigation Bar
> When the user changes the top-level view controller, the navigation controller updates the navigation bar accordingly. Specifically, the navigation controller updates the bar button items displayed in each of the three navigation bar positions: left, middle, and right. Bar button items are instances of the UIBarButtonItem class. You can create items with custom content or create standard system items depending on your needs. For more information about how to create bar button items, see UIBarButtonItem Class Reference.
> 
> For all but the root view controller on the navigation stack, the item on the left side of the navigation bar provides navigation back to the previous view controller. The contents of this left-most button are determined as follows:
> 
> If the new top-level view controller has a custom left bar button item, that item is displayed. To specify a custom left bar button item, set the leftBarButtonItem property of the view controller’s navigation item.
> 
> If the top-level view controller does not have a custom left bar button item, but the navigation item of the previous view controller has an object in its backBarButtonItem property, the navigation bar displays that item.
> 
> If a custom bar button item is not specified by either of the view controllers, a default back button is used and its title is set to the value of the title property of the previous view controller—that is, the view controller one level down on the stack. (If there is only one view controller on the navigation stack, no back button is displayed.)
> 
> NOTE
> 
> In cases where the title of a back button is too long to fit in the available space, the navigation bar may substitute the string “Back” for the actual button title. The navigation bar does this only if the back button is provided by the previous view controller. If the new top-level view controller has a custom left bar button item—an object in the leftBarButtonItem or leftBarButtonItems property of its navigation item—the navigation bar does not change the button title.
> 
> The navigation controller updates the middle of the navigation bar as follows:
> 
> If the new top-level view controller has a custom title view, the navigation bar displays that view in place of the default title view. To specify a custom title view, set the titleView property of the view controller’s navigation item.
> 
> If no custom title view is set, the navigation bar displays a label containing the view controller’s default title. The string for this label is usually obtained from the title property of the view controller itself. If you want to display a different title than the one associated with the view controller, set the title property of the view controller’s navigation item instead.
> 
> The navigation controller updates the right side of the navigation bar as follows:
> 
> If the new top-level view controller has a custom right bar button item, that item is displayed. To specify a custom right bar button item, set the rightBarButtonItem property of the view controller’s navigation item.
> 
> If no custom right bar button item is specified, the navigation bar displays nothing on the right side of the bar.
> 
> The navigation controller updates the navigation bar each time the top view controller changes. Thus, these changes occur each time a view controller is pushed onto the stack or popped from it. When you animate a push or pop operation, the navigation controller similarly animates the change to the navigation bar content.
> 
> Tinting of the navigation bar is controlled by properties of the navigation bar itself. Use the tintColor property to change the tint color of items in the bar and use the barTintColor property to change the tint color of the bar itself. Navigation bars do not inherit their tint color from the currently displayed view controller.
> 
> For more information about the navigation bar, see UINavigationBar Class Reference.

Source: [Apple](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UINavigationController_Class/)

Note: also worth it to read the next part regarding the middle and right barButtonItems
