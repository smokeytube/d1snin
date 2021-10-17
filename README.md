```kotlin
@Bean
fun d1snin(): Human = developer {
    general {
        gender = Gender.MALE
        name = "Mikhail Koshkin"
        age = 15
    }

    knowledge {
        languages {
            language {
                name = "Kotlin"
                experienceYears = 0.5
            }

            language {
                name = "Java"
                experienceYears = 1.0
            }
        }

        frameworks {
            framework {
                name = "Spring Framework"
                modules = listOf(
                    "core",
                    "data",
                    "web",
                    "security",
                    "cloud"
                )
                experienceYears = 0.2
            }
        }
    }

    contacts {
        contact {
            service = "discord"
            address = "d1snin#3007"
        }

        contact {
            service = "e-mail"
            address = listOf("~", "@", "d1s.uno").joinToString()
        }

        contact {
            service = "slack-connect"
            address = "d1snin@aol.com"
        }

        contact {
            service = "telegram"
            address = "@d1snin"
        }
    }
}

@DslMarker
annotation class DeveloperDslMarker

@DeveloperDslMarker
open class Human {
    lateinit var gender: Gender
    lateinit var name: String
    var age by Delegates.notNull<Int>()
}

enum class Gender {
    MALE, WOMAN
}

@DeveloperDslMarker
open class Knowledge {
    lateinit var name: String
    var experienceYears by Delegates.notNull<Double>()
}

@DeveloperDslMarker
class Language : Knowledge()

@DeveloperDslMarker
class Framework : Knowledge() {
    lateinit var modules: List<String>
}

@DeveloperDslMarker
class LanguageContext(
    val dev: Developer
) {
    inline fun language(languageCtx: Language.() -> Unit) =
        this.dev.languages.add(Language().apply(languageCtx))
}

@DeveloperDslMarker
class FrameworkContext(
    val dev: Developer
) {
    inline fun framework(frameworkCtx: Framework.() -> Unit) =
        this.dev.frameworks.add(Framework().apply(frameworkCtx))
}

@DeveloperDslMarker
class KnowledgeContext(
    val dev: Developer
) {
    inline fun languages(languageCtx: LanguageContext.() -> Unit) =
        languageCtx(LanguageContext(dev))

    inline fun frameworks(frameworkCtx: FrameworkContext.() -> Unit) =
        frameworkCtx(FrameworkContext(dev))
}

@DeveloperDslMarker
class Contact {
    lateinit var service: String
    lateinit var address: String
}

@DeveloperDslMarker
class ContactContext(
    val dev: Developer
) {
    inline fun contact(contactCtx: Contact.() -> Unit) =
        dev.contacts.add(Contact().apply(contactCtx))
}

@DeveloperDslMarker
class Developer : Human() {
    val languages = mutableListOf<Language>()
    val frameworks = mutableListOf<Framework>()
    val contacts = mutableListOf<Contact>()

    companion object {
        inline fun developer(developerCtx: Developer.() -> Unit): Developer =
            Developer().apply(developerCtx)
    }

    inline fun general(humanCtx: Human.() -> Unit) =
        this.apply(humanCtx)

    inline fun knowledge(knowledgeCtx: KnowledgeContext.() -> Unit) =
        knowledgeCtx(KnowledgeContext(this))

    inline fun contacts(contactCtx: ContactContext.() -> Unit) =
        contactCtx(ContactContext(this))
}
```
`/ I think I overdid it. /`

[![wakatime](https://github-readme-stats.vercel.app/api/wakatime?username=d1snin&theme=dracula&v=2)](https://github.com/d1snin)

`(c) By Jacob Herd. (https://toxicaven.dev/)`
[![yes.](https://media.discordapp.net/attachments/835130373209849918/895776013559164938/5pn1ui.png)](https://github.com/d1snin)

