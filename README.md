## Typeahead

Um simples projeto a fim de estudos do RXJS. 

Um typeahead utilizando o poder do RXJS a fim de torna-lo reativo.

Neste projeto foram utilizados do RXJS as funções e operadores ``fromEvent, ajax, map, switchMap, of, catchError, startWith, debounceTime e distinctUntilChanged.``




**Foram adicionadas trativas de erro:**
 - Quando a API retorna erro a lista de resultados é ocultada. Foi feio o uso do ``catchError`` para capturar o erro e retornar o stream com todas as trativas adicionadas.
 - Busca repetida é ignorada. Utilizando o operador ``distinctUntilChanged`` é possível ignorar a busca de palavras repetidas, afim de evitar requisições desnecessárias.
 - Foi usado o ``debounceTime`` para evitar que varios eventos sejam disparados. O script aguarda um tempo de 300ms sem atividade do usuário e o ``switchMap`` evita que várias subinscrições sejam criadas, cancelando as outras sempre que um novo evento é emitido.