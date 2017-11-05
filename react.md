# React

#### Pass native HTML props through custom components
You're building a custom button component and are using the native HTML5 button element. 
You set up your props as needed but here's the issue. Since you're using the native button element, 
the attributes that belong to that button should be available through your Button component, right?

Nope. By defining your custom props, you're overriding the native HTML attributes. The fix? 
You'll need to allow the native HTML attributes to pass through. Let's destructure the props object.
The variable htmlProps is a collection of all the props that were passed through the Button 
component, but not explicity defined here.

```
{ type, size, icon, active, disabled, children, className, ...htmlProps } = this.props;
```

Then pass through the htmlProps as a rest operator to the native button element.
```
return (
    <button type={htmlType} disabled={disabled} {...htmlProps}>
        {children}
    </button>
);
```

Note: There may be some cases where the props in htmlProps is unknown to the native button element.
The console will be sure to let you know. One way to ensure that the htmlProps that you're passing
through can be understood by the button element is to remove the props that the native button element
does not understand. 

Define the props in the propTypes object.

```
Button.propTypes = {
    className: PropTypes.string,
    type: PropTypes.oneOf(['primary', 'secondary']),
    size: PropTypes.oneOf(['small', 'medium', 'large']),
    icon: PropTypes.string,
    active: PropTypes.bool,
    disabled: PropTypes.bool,
    children: PropTypes.node,
};
```

Then do a deep object comparison with lodash's omit function. You can write your own deep comparison
function instead if a third party library like lodash is not available.

```
const nativeAttrs = omit(htmlProps, ...Object.keys(Button.propTypes));
```

Once the htmlProps object has been "cleaned up" and reassigned to nativeAttrs, 
pass through nativeAttrs to the button.
```
return (
    <button type={htmlType} disabled={disabled} {...nativeAttrs}>
        {children}
    </button>
);
```