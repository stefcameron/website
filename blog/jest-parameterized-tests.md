# Jest parameterized tests

<details>

```yaml
summary: 'How to write parameterized tests in Jest'
updated: '2020/06/16'
```
</details>

I never knew you could do this:

```javascript
[sizes.SMALL, sizes.MEDIUM].forEach((size) => {
  Object.values(statuses).filter((status) => status !== statuses.NONE).forEach((status) => {
    it(`has role="${ariaRoles.ALERT_DIALOG}" when size = ${size} and status = ${status}`, () => {
      render(<TestModal size={size} status={status} />);
      expect(screen.queryByRole(ariaRoles.ALERT_DIALOG)).toBeTruthy();
    });
  });
});
```

and have it generate a bunch of tests resulting in:

```
✓ has role="alertdialog" when size = SMALL and status = SUCCESS (104 ms)
✓ has role="alertdialog" when size = SMALL and status = WARNING (110 ms)
✓ has role="alertdialog" when size = SMALL and status = ERROR (107 ms)
✓ has role="alertdialog" when size = MEDIUM and status = SUCCESS (101 ms)
✓ has role="alertdialog" when size = MEDIUM and status = WARNING (107 ms)
✓ has role="alertdialog" when size = MEDIUM and status = ERROR (109 ms)
```

I just discovered parameterized tests! Awesome sauce! 💪

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=jest-parameterized-tests&template=blog-post-discussion.md&labels=discussion)
