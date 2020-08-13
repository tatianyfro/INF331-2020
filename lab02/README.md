## Lab02 - Data Flow & Mensagens
* Tatiany F. R. Oliveira </br></b>

### Tarefa sobre catálogo de componentes 
[Baixe aqui o notebook com a resolução das seis tarefas](notebook/components-01-catalog.ipynb)
<a href="notebook/components-01-catalog(1).ipynb"> Baixe aqui o notebook com a resolução das seis tarefas. </a>


### Tarefa Web Components 1 
~~~html

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
