# msg-consumer_111018
### url publisher

104.198.163.13:5672

### Exchange Info

**name:** stock_data
**type:** topic
**routing key:** stocks
**durable:** true

### published data

Data is a stringify json object

Array type of
Data model
```
{
	title: string,
	company: string,
	ticker: string,
	source: string,
	last: number,
	dt: string, // datetime
	volume: number
}
```
**RabbitMq tutorial**
[http://www.rabbitmq.com/getstarted.html](http://www.rabbitmq.com/getstarted.html)

## Tareas por realizar
- Realizar aplicacion que consuma datos desde instancia de RabbitMq e ingrese dichos datos en base de datos MongoDB con el siguiente modelo. Tener en cuenta que recibira un array y la idea es que cada elemento de ese array se guarde como un registro en base de datos

```
{
  _id: ObjectId
	title: string,
	company: string,
	ticker: string,
	source: string,
	last: number,
	dt: string, // datetime
	volume: number
}
```
- Realizar un API Rest que genere 3 url
  - GET lista de registros, ex: /api/stocks?count=100&skip=4
    - *count*: number, cantidad de registros solicitados
    - *skip*: number, parametro indica indice de base 0 para desplazarse en array de registros
  - GET registro por id (string), ex: /api/stocks/abc123def34234
  - GET registro con filtro de texto para campo title. La idea de esta url es traer por medio del filtro un array en el cual se pueda ver la progrsion del valor de la accion para dicha compania filtrada ex: /api/stocks?title=Netflix
