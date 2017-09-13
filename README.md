# formazione-sicurezza-clicker
I videocorsi di formazionesicurezza.com sono tagliati ogni 40 secondi per cercare di assicurare che il lavoratore prenda davvero coscienza dei propri diritti e doveri in ambito della sicurezza sul lavoro.

Se invece anche tu non hai rispetto per la tua salute, esercita il tuo diritto all'ignoranza usando questo script che automatizza l'operazione permettendoti di fare altro mentre i video proseguono in background.

## Istruzioni

  _ATTENZIONE: L'autore non si assume nessuna responsabilità sulle conseguenze dell'uso di questo script._

1. Vai nella pagina con i video, fai click destro sul pulsante play e seleziona "Ispeziona Elemento" (o funzione equivalente per browser diversi da Chrome). Questo è necessario affinchè il codice dopo trovi correttamente il tasto.

2. Incolla nella console del browser (si trova nella parte nuova che si apre all'esecuzione del punto precedente) questo script e premi `Invio`:

```javascript
function hehehe(){
	var x = document.getElementsByClassName("playbarBigButton")[0];

	if (!x){
		console.log("Non ho trovato il tasto play, trovalo con l'inspector!")
		return
	}

	if (x.title == "Play"){
		var over = document.createEvent('MouseEvents')
		over.initMouseEvent('mouseover', true, false, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);

		var click = document.createEvent('MouseEvents')
		click.initMouseEvent('click', true, false, window, 1, 0, 0, 0, 0, false, false, false, false, 0, null);

		x.dispatchEvent(over)
		x.dispatchEvent(click)
		console.log("Click! Hehe")
	}
}
hehehe()
setInterval(hehehe, 1000);
```

3. NON aprire altre tab in quella finestra del browser, o, se hai già altre tab aperte, "trascina" la tab del videocorso in una nuova finestra. Questo serve perchè, nelle tab coperte dalla tab attiva, il browser può decidere per ragioni di performance di bloccare l'esecuzione del javascript finchè l'utente non la riporta in primo piano. Mettendo la tab in una finestra separata, questo problema si risolve perchè, anche se l'intera finestra del browser è nascosta da altre finestre, il browser non applica questa ottimizzazione.

4. Enjoy


**PS: Se è stato un tuo superiore a linkarti questo script, probabilmente è nel tuo interesse non usarlo.**
