# NetJava
const __dirname = path.dirname(new URL(import.meta.url).pathname);

const __dirname = path.dirname(new URL(import.meta.url).pathname); 
 ^^^^^ should be vvvvvv
const __dirname = fileURLToPath(new URL('.', import.meta.url))

 1
Sum should = item.price * item.quantity
 Should be new LocalTimeDate() otherwise shows wrong time by 1 hour
 Doesn't save to file, should be __dirname

 2
 Doesn't log anything

 3
 Shows wrong time by one hour, should be offset by one hour +
 Timeout is unnecessary and removing it makes endpoint go faster

 4
 doesn't add to order
Doesn't save to file

 5
 Why have calculatedAmount when you already have totalAmount

 6
 Asks for query but doesn´t have it in the URL so you can't use it to filter

 7
 Should be patch because it's just one thing
 Will always throw error because orders doesn't get saved to
 Should be "There are no orders"

 8

 9

 10
 has no Error handling for null id param
 Hjälpfunktion
 Borde iterera items.quantity istället för 10000