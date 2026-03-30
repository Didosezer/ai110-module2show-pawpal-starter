/*
 *
 * This file exports a string containing a Mermaid `classDiagram` that
 * represents the four main objects: Owner, Pet, Task, Scheduler.
 *
 * To render: paste the string into a Mermaid renderer, use it inside a
 * Markdown file that supports Mermaid, or import it into a small web page
 * that initializes Mermaid.
 */


        ```mermaid
        classDiagram
            class Owner {
                +name: String
                +pets: List~Pet~
                +add_pet(pet: Pet)
                +remove_pet(pet_or_name)
            }
            class Pet {
                +name: String
                +tasks: List~Task~
                +add_task(task: Task)
                +remove_task(task_or_name)
            }
            class Task {
                +name: String
                +time: DateTime
                +is_done: bool
                +mark_done()
            }
            class Scheduler {
                +owner: Owner
                +get_schedule(date_filter = null, include_done = false)
            }

            Owner "1" o-- "*" Pet : owns
            Pet "1" o-- "*" Task : has
            Scheduler --> Owner : manages
        ```

