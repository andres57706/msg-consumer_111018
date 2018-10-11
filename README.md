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
- Realizar aplicacion que consuma datos desde instancia de RabbitMq e ingrese dichos datos en base de datos MongoDB con el siguiente modelo

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
  - GET registro con filtro de texto para campo title. ex: /api/stocks?title=Netflix
