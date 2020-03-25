const fib = async n => {
  //yield point
  await new Promise(resolve => setTimeout(resolve, 1));
  switch (n) {
    case 1:
      return 0;
    case 2:
      return 1;
    default:
      return (await fib(n - 1)) + (await fib(n - 2));
  }
};

const fibs = async n => {
  const result = await fib(n);
  console.log(result);
  process.exit(1);
};

const spinner = async () => {
  const spinnerString = "\\\r-\r/\r|\r";
  const printSpinnerChar = index => {
    return new Promise(resolve =>
      setTimeout(() => {
        process.stdout.write(spinnerString.charAt(index % 8));
        resolve();
      }, 10)
    );
  };
  for (let i = 0; ; i++) {
    await printSpinnerChar(i);
  }
};

spinner();
fibs(20);
