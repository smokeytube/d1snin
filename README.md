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
```

[![wakatime](https://github-readme-stats.vercel.app/api/wakatime?username=d1snin&theme=dracula&v=2)](https://github.com/d1snin)

`(c) By Jacob Herd. (https://toxicaven.dev/)`
[![yes.](https://media.discordapp.net/attachments/835130373209849918/895776013559164938/5pn1ui.png)](https://github.com/d1snin)

