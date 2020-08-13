## Lab02 - Data Flow & Mensagens
* Tatiany F. R. Oliveira </br></b>

### Tarefa sobre catálogo de componentes 
[Baixe aqui o notebook com a resolução das seis tarefas](notebook/components-01-catalog.ipynb)
</br>
### Tarefa Web Components 1 
~~~html
<dcc-trigger label="Mundo" style="background-color:green;padding: 5px 15px;font-weight: bold;" action="noticia/mundo/ciencias" value="Notícias do Mundo - Ciências"></dcc-trigger>
<dcc-trigger label="Brasil P" style="background-color:yellow;padding: 5px 15px;font-weight: bold;" action="noticia/brasil/politica" value="Notícias do Brasil - Política"/></dcc-trigger>
</br>
<dcc-trigger label="Bahia" style="background-color:tomato;padding: 5px 15px;font-weight: bold;" action="noticia/bahia/turismo" value="Notícias da Bahia - Turismo"/></dcc-trigger>
<dcc-trigger label="Brasil E" style="background-color:blue;padding: 5px 15px;font-weight: bold;" action="noticia/brasil/economia" value="Notícias do Brasil - Economia"/></dcc-trigger>

<dcc-lively-talk delay="delay" character="doctor" speech="Eu leio "><subscribe-dcc topic="#/politica"/></dcc-lively-talk>
<dcc-lively-talk delay="delay" character="nurse" speech="Eu leio "><subscribe-dcc topic="noticia/brasil/#"/></dcc-lively-talk>
<dcc-lively-talk delay="delay" character="patient" speech="Eu leio "><subscribe-dcc topic="noticia/#"/></dcc-lively-talk>
~~~
</br>

### Tarefa Web Components 2  
~~~html
<dcc-trigger label="Noticias" 
              action="next/rss"></dcc-trigger>
<dcc-rss source="https://www.wired.com/category/science/feed" 
        publish="rss/science">  <subscribe-dcc topic="next/rss" 
        role="step"></subscribe-dcc></dcc-rss>
<dcc-rss source="https://www.wired.com/category/design/feed" 
          publish="rss/design">
<subscribe-dcc topic="next/rss" role="step"></subscribe-dcc></dcc-rss>
<dcc-aggregator publish="aggregate/science" quantity="3">
<subscribe-dcc topic="rss/science"></subscribe-dcc></dcc-aggregator>
<dcc-lively-talk delay="delay" character="doctor" ><subscribe-dcc topic="aggregate/science"/></dcc-lively-talk>
<dcc-lively-talk delay="delay" character="nurse" ><subscribe-dcc topic="rss/science"/></dcc-lively-talk>
<dcc-lively-talk delay="delay" character="patient" ><subscribe-dcc topic="rss/design"/></dcc-lively-talk>
~~~
