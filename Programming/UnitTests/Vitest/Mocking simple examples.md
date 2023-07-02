# Example of mocking a function

## Mocking a module that contain a function that return a function.

Code to mock :

```js
const HTTP: AxiosInstance = axios.create(config);

const apiFunc = async (a, b, c) => {
  const res = await HTTP(a, b, c);
  return res.data;
};
```

Mocked Code :

```js
HTTPmock.mockResolvedValue({
  data: "foobar",
});

vi.mock("axios", () => ({
  default: {
    create: () => () => HTTPmock(),
  },
}));

test("test", async () => {
  HTTPmock.mockResolvedValue("test");
  const result = await apiFunc();
  expect(result).toBe({
    data: "foobar",
  });
});
```
