# Forms in React

## Control an input field

1. **Bind** 🔗 the value of the input **to the state**
2. **Change the state** itself when the input fires an **onChange** 👂 event.

Check out the [interactive example](https://codepen.io/vikvikvr/pen/YzZQJZZ) 👈

```js
const Form = () => {
  const [name, setName] = useState('');

  const handleChange = (event) => {
    setName(event.target.value);
  };

  return <input value={name} onChange={handleChange} type="text" />;
};
```

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
    const { name, value } = event.target;
    const stateChange = { [name]: value };
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
