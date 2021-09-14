# You can rename props while destructuring them

Sometimes components have conflicting prop names. This showed up when using [material-ui](https://material-ui.com/). 
I decided to attempt to make my own component based on an existing one, and dynamically import existing props if they exist.
With Material-UI however I have been using the word classes consistently in my coding, so bringing it in as props wasn't working, but renaming them worked!

```
function ThemeButton({ ...props }) {
  const classes = useStyles();
  const { onClick, type, to, title, classes: classList } = props;

  return (
    <Button
      type={type || ''}
      className={`${classes.root} ${classList && classes[classList]}`}
      variant="contained"
      component={to ? Link : 'span'}
      to={to}
      onClick={onClick}
    >
      {title}
    </Button>
  );
}

export default ThemeButton;
```