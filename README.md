# ToDo app

## Kuidas paigaldada?

* Installi ember `npm install -g ember-cli` 
* Loo uus emberi projekt `ember new toDo`
* `cd toDo`
* `npm install`
* `ember serve`
* Installi mirage `ember install ember-cli-mirage`

Rakenduse muutmiseks selle toimimise ajal tuleb avada ka teine cmd.



* Genereerime route 
* `ember g route tasks`

* `import Route from '@ember/routing/route';


`export default Route.extend({

    model(){
        return this.store.findAll('task');
    },
    actions:{
        addTask() {

            if (this.get('controller').get('task')) {
                this.get('store').createRecord("task", {
                    id:Date.now(),
                    title: this.get('controller').get('task'),
                    isdone: false
                });
            }
            this.get('controller').set('task', "");

        }
}});`

* Genereerime modeli
* `ember g model task`

`import DS from 'ember-data';

export default DS.Model.extend({
    title:DS.attr('string'),
    isdone:DS.attr('boolean')
});`
