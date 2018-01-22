# Accessibility

1. **Describe user interface controls:** Provide content descriptions for user interface components that do not have visible text, particularlyImageButton, ImageView and CheckBox components. Use the `android:contentDescription` XML layout attribute or the `setContentDescription(CharSequence)` method to provide this information for accessibility services. (Exception: decorative graphics) Many accessibility services, such as TalkBack and BrailleBack, automatically announce an element's type after announcing its label, so you shouldn't include element types in your labels. For example, `submit` is a good label for a Button object, but `submitButton` isn't a good label.

2. **Enable focus-based navigation:** Make sure users can navigate your screen layouts using hardware-based or software directional controls (D-pads, trackballs, keyboards and navigation gestures). In a few cases, you may need to make user interface components focusable or change the focus order to be more logical for user actions. In order to enable this form of navigation, all navigational elements that the user should be able to navigate to need to be set as focusable. This modification can be done at runtime using the `View.setFocusable()` method on that UI control, or by setting the `android:focusable` attrubute in your XML layout files. Also, each UI control has 4 attributes, `android:nextFocusUp`, `android:nextFocusDown`, `android:nextFocusLeft`, and `android:nextFocusRight`, which you can use to designate the next view to receive focus when the user navigates in that direction. For more info https://developer.android.com/training/accessibility/accessible-app.html#focus 

3. **Text field hints:** For EditText fields, provide an `android:hint` attribute instead of a content description, to help users understand what content is expected when the text field is empty and allow the contents of the field to be spoken when it is filled.

4. **Controls that change function:** If you have buttons or other controls that change function during the normal activity of a user in your application (for example, a button that changes from Play to Pause), make sure you also change the `android:contentDescription` of the button appropriately.

5. **Sets of small controls:** If you have controls that are smaller than the minimum recommended touch size in your application screens, consider grouping these controls together using a ViewGroup and providing a `android:contentDescription` for the group.

6. **Decorative images and graphics:** Elements in application screens that are purely decorative and do not provide any content or enable a user action should not have accessibility content descriptions. For graphical elements that are purely decorative, set their respective `android:contentDescription` XML attributes to `@null`. If your app only supports devices running Android 4.1 (API level 16) or higher, you can instead set these elements' `android:isImportantForAccessibility` XML attributes to `no`.

7. **Label for:** If your app is installed on a device running Android 4.2 (API level 17) or higher, use the `android:labelFor` attribute when labeling View objects that serve as content labels for other View objects.

8. **Grouping content:** You should arrange related content into groups so that accessibility services announce the content in a way that reflects its natural groupings. Users of assistive technology then don't need to swipe, scan, or wait as much to discover all information on the screen.

9. **Touch targets:** In general, you want the touchable area of focusable items to be a minimum of `48dp x 48dp`. Larger is even better.

10. **Testing:** After finishing testing, test the app using Node Tree  Debugging. https://developer.android.com/guide/topics/ui/accessibility/node-tree-debugging.html
