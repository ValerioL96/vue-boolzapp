Milestone 1

1) Replica della grafica con la possibilità di avere messaggi scritti dall’utente (verdi) e dall’interlocutore (bianco) assegnando due classi CSS diverse:

1.1) Creo in html due sezioni in cui in una avrò i messaggi con i conttati e nell'altra la chat dei singoli:

- < div id="app">
            < div class="container">
                < section class="chat-wrapper">
                    

                < /section>

                < section class="messages-contacts">

                < /section>
            </div>
        </div>

1.2) creo in javascript una lista dei contatti in cui mi do anche un indice iniziale:

- const { createApp } = Vue

  createApp({
    data() {
      return {

        activeIndex : 0,
        contacts: [
            {
                name: 'Michele',
                avatar: 'img/avatar_1.jpg',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Hai portato a spasso il cane?',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'Ricordati di stendere i panni',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 16:15:22',
                        message: 'Tutto fatto!',
                        status: 'received'
                    }
                ],
            },
            {
                name: 'Fabio',
                avatar: './img/avatar_2',
                visible: true,
                messages: [
                    {
                        date: '20/03/2020 16:30:00',
                        message: 'Ciao come stai?',
                        status: 'sent'
                    },
                    {
                        date: '20/03/2020 16:30:55',
                        message: 'Bene grazie! Stasera ci vediamo?',
                        status: 'received'
                    },
                    {
                        date: '20/03/2020 16:35:00',
                        message: 'Mi piacerebbe ma devo andare a fare la spesa.',
                        status: 'sent'
                    }
                ],
            },
            {
                name: 'Samuele',
                avatar: './img/avatar_3',
                visible: true,
                messages: [
                    {
                        date: '28/03/2020 10:10:40',
                        message: 'La Marianna va in campagna',
                        status: 'received'
                    },
                    {
                        date: '28/03/2020 10:20:10',
                        message: 'Sicuro di non aver sbagliato chat?',
                        status: 'sent'
                    },
                    {
                        date: '28/03/2020 16:15:22',
                        message: 'Ah scusa!',
                        status: 'received'
                    }
                ],
            },
            {
                name: 'Alessandro B.',
                avatar: './img/avatar_4',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Lo sai che ha aperto una nuova pizzeria?',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'Si, ma preferirei andare al cinema',
                        status: 'received'
                    }
                ],
            },
            {
                name: 'Alessandro L.',
                avatar: './img/avatar_5',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Ricordati di chiamare la nonna',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'Va bene, stasera la sento',
                        status: 'received'
                    }
                ],
            },
            {
                name: 'Claudia',
                avatar: './img/avatar_6',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Ciao Claudia, hai novità?',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'Non ancora',
                        status: 'received'
                    },
                    {
                        date: '10/01/2020 15:51:00',
                        message: 'Nessuna nuova, buona nuova',
                        status: 'sent'
                    }
                ],
            },
            {
                name: 'Federico',
                avatar: './img/avatar_7',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Fai gli auguri a Martina che è il suo compleanno!',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'Grazie per avermelo ricordato, le scrivo subito!',
                        status: 'received'
                    }
                ],
            },
            {
                name: 'Davide',
                avatar: './img/avatar_8',
                visible: true,
                messages: [
                    {
                        date: '10/01/2020 15:30:55',
                        message: 'Ciao, andiamo a mangiare la pizza stasera?',
                        status: 'received'
                    },
                    {
                        date: '10/01/2020 15:50:00',
                        message: 'No, l\'ho già mangiata ieri, ordiniamo sushi!',
                        status: 'sent'
                    },
                    {
                        date: '10/01/2020 15:51:00',
                        message: 'OK!!',
                        status: 'received'
                    }
                ],
            }
        ]
        
      }
    }
  }).mount('#app')

1.3) nella sezione chat creo il collegamento con il contatto con indice 0:

- < section class="chat-wrapper">
    < div class="contact-chat flex">
                        
        < article class="picture-name flex">
            < img class="picture-contact" :src="contacts[activeIndex].avatar" :alt="contacts[activeIndex].name">
                < div class="text">
    
                    < h3>
                        {{contacts[activeIndex].name}}
                    < /h3>
                    < p>ultimo accesso oggi alle 12:00< /p>
    
                < /div>
        < /article>
        < article class="toolbar flex">
            < i class="fa-solid fa-magnifying-glass">< /i>
            < i class="fa-solid fa-paperclip">< /i>
            < i class="fa-solid fa-ellipsis-vertical">< /i>
        < /article>
                       
    < /div>
    
 < /section>

1.4) creo nella sezione chat-wrapper un div.chat

- < section class="chat-wrapper">
    < div class="contact-chat flex">
                        
        < article class="picture-name flex">
            < img class="picture-contact" :src="contacts[activeIndex].avatar" :alt="contacts[activeIndex].name">
                < div class="text">
    
                    < h3>
                        {{contacts[activeIndex].name}}
                    < /h3>
                    < p>ultimo accesso oggi alle 12:00< /p>
    
                < /div>
        < /article>
        < article class="toolbar flex">
            < i class="fa-solid fa-magnifying-glass">< /i>
            < i class="fa-solid fa-paperclip">< /i>
            < i class="fa-solid fa-ellipsis-vertical">< /i>
        < /article>
                       
    < /div>

    < div class="chat">
    < /div>
    
 < /section>

 1.5) creo nel div.chat due artcle in cui in uno aggiungo due div, per i messaggi di invio e quelli ricevuti con classi differenti per dare posizione e colore differente in chat, mentre nell'altro article aggiungo la barra testo che successivamente mi servirà per aggiungere nuovo contenuto in chat:

 - < div class="chat">
        < article class="chat-view">
            < div class="sent flex">
                < p>Hai portato a spasso il cane?< /p>
                < p>Ricordati di stendere i panni< /p>
            < /div>
            < div class="received flex">
                < p>Tutto fatto!< /p>
            < /div>

        < /article>
        < article class="write-message flex">
            < i class="fa-regular fa-face-smile">< /i>
            < input type="text" name="sent-message" id="sent-message" placeholder="Scrivi un messaggio">
            < i class="fa-solid fa-microphone">< /i>
        < /article>
    < /div>

2) Visualizzazione dinamica della lista contatti: tramite la direttiva v-for, visualizzare nome e immagine di ogni contatto:

2.1) creo  nella section.messages-contacts un div.contacts in cui aggiungo una lista ul che sarà collegata  tramite v-for al mio array a cui darò degli index:

-  < div class="contacts">
        < ul>
            < li v-for="item in contacts" :key="index" class="flex">
                < img class="picture-contact" :src="item.avatar" alt="item.name">
                < div class="text">
    
                    < h3>
                        {{item.name}}
                    < /h3>
                    < p>ultimo messaggio inviato< /p>
    
                < /div>

            < /li>
        < /ul>
   < /div>


Milestone 2

Visualizzazione dinamica dei messaggi: tramite la direttiva v-for, visualizzare tutti i messaggi relativi al contatto attivo all’interno del pannello della conversazione


2) Click sul contatto mostra la conversazione del contatto cliccato:

2.1) aggiungo una condizione al ciclo for dei contatti, se index è uguale ad activeIndex si avrà .active altrimenti nulla:

-  < div class="contacts">
        < ul>
            < li v-for="(item, index) in contacts" :key="index" class="flex"
                 :class="(index === activeIndex) ? 'active' : ''">
                < img class="picture-contact" :src="item.avatar" alt="item.name">
                < div class="text">

                    < h3>
                        {{item.name}}
                    < /h3>
                    < p>ultimo messaggio inviato< /p>

                < /div>

            < /li>
        < /ul>
    < /div>

2.2) creo in javascript una funzione che mi permette di aprire la chat dei contatti:

-  methods:{
        changeContacts: function(contactsIndex){
            this.activeIndex = contactsIndex;
        }
    }


2.3) aggiungo al v-for la funzione click che mi permette di svolgere l'azione del punto 2.2 ogni volta che clicco sul contatto scelto:

- < div class="contacts">
        < ul>
            < li v-for="(item, index) in contacts" :key="index" class="flex"
                 :class="(index === activeIndex) ? 'active' : ''"
                 @click="changeContacts(index)">
                < img class="picture-contact" :src="item.avatar" alt="item.name">
                < div class="text">

                    < h3>
                        {{item.name}}
                    < /h3>
                    < p>ultimo messaggio inviato< /p>

                < /div>

            < /li>
        < /ul>
    < /div>




Milestone 3

1) Aggiunta di un messaggio: l’utente scrive un testo nella parte bassa e digitando “enter” il testo viene aggiunto al thread sopra, come messaggio verde:

1.1) creo una funzione che mi aggiunga un nuovo task:

- methods:{
        changeContacts: function(contactsIndex){
            this.activeIndex = contactsIndex;
        },
        addNewTask: function(){
            const newTask={
                message: '',
                status: 'sent'
            }
          }
    }

1.2) aggiungo un v-modell al mio input in chat per creare un collegamento tra l'input e la variabile, che aggiungo nel data:

-  < input type="text" name="sent-message" id="sent-message" placeholder="Scrivi un messaggio" 
           v-model= "newTaskMessage">

-  newTaskMessage:'',

1.3) creo una variabile nella funzione in modo che ogni volta che la chiama la passa:

-  methods:{
        changeContacts: function(contactsIndex){
            this.activeIndex = contactsIndex;
        },
        addNewTask: function(newMessage){
            const newTask={
                message: newMessage,
                status: 'sent'
            }
            this.contacts.push(newTask);
            this.clearNewTask();
          },
          clearNewTask: function(){
            this.newTaskMessage= '';
          }
    }

1.4) vado ad aggiungere in input la funzione keyup.enter:

- < input type="text" name="sent-message" id="sent-message" placeholder="Scrivi un messaggio" 
           v-model= "newTaskMessage"
           @keyup.enter = "addNewTask(newTaskMessage)">
 


2) Risposta dall’interlocutore: ad ogni inserimento di un messaggio, l’utente riceverà un “ok” come risposta, che apparirà dopo 1 secondo.

Milestone 4
Ricerca utenti: scrivendo qualcosa nell’input a sinistra, vengono visualizzati solo i contatti il cui nome contiene le lettere inserite (es, Marco, Matteo Martina -> Scrivo “mar” rimangono solo Marco e Martina)



                    