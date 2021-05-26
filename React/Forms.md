# Forms in React

## Control an input field

You want to bind the value of the input to the state, and change the state itself when the input fires an onChange event.

<p class="codepen" data-height="298" data-theme-id="light" data-default-tab="js,result" data-user="vikvikvr" data-slug-hash="YzZQJZZ" style="height: 298px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="React input">
  <span>See the Pen <a href="https://codepen.io/vikvikvr/pen/YzZQJZZ">
  React input</a> by vikvikvr (<a href="https://codepen.io/vikvikvr">@vikvikvr</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Control multiple input fields

When dealing with multiple input fields, you can generalize the onChange handling by addressing the properties name and value available inside the event object itself.

```js
const BigForm = () => {
  const [form, setForm] = useState({
    firstName: '',
    lastName: '',
    age: 18
  });

  const handleChange = (event) => {
    // grab name and value of the input that has changed
    const { name, value } = event.target;
    // build a piece of the updated form
    // object with a dynamic key
    const stateChange = { [name]: value };
    // merge the change with the current form data
    setForm({ ...form, ...stateChange });
  };

  const handleSubmit = (event) => {
    // prevent browser tab from refreshing, causing our app to restart
    event.preventDefault();
    console.log('submitting', form);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={form.firstName}
        name="firstName"
        onChange={handleChange}
        type="text"
      />
      <input
        value={form.lastName}
        name="lastName"
        onChange={handleChange}
        type="text"
      />
      <input
        value={form.age}
        name="age"
        onChange={handleChange}
        type="number"
      />
      <input type="submit" value="submit" />
    </form>
  );
};
```
