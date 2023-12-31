
# TxkyoGhxul

```csharp

public record InviteMeToJobCommand(string Company, decimal Salary) : IUpdateCommand<User>;

public class InviteMeToJobCommandHandler : IUpdateCommandHandler<InviteMeToJobCommand, User>
{
    private readonly IRepository<User> _repository;
    private readonly IUnitOfWork _unitOfWork;
    private readonly ILogger<InviteMeToJobCommandHandler> _logger;

    public InviteMeToJobCommandHandler(IRepository<User> repository, IUnitOfWork unitOfWork, ILogger<InviteMeToJobCommandHandler> logger)
    {
        _repository = repository ?? throw new ArgumentNullException(nameof(repository));
        _unitOfWork = unitOfWork ?? throw new ArgumentNullException(nameof(unitOfWork));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<Result<User>> Handle(InviteMeToJobCommand request, CancellationToken cancellationToken)
    {
        var me = await _repository.GetAsync(user => user.Surname == "Pomin", cancellationToken);
        if (me == null)
        {
            return new EntityNotFoundException(typeof(User));
        }

        me.GotJobWithSalary(request.Salary);
        await _repository.UpdateAsync(me, cancellationToken);

        await _unitOfWork.SaveChangesAsync(cancellationToken);

        _logger.LogInformation("I'm happy to work in company : {Company}", request.Company);

        return me;
    }
}

```

---

# Languages 📢:
  - English 🇬🇧
  - Russian 🇷🇺

---

## English 🇬🇧
### :man_technologist: About me:
<p>
  Hello! My name is Sasha Pomindeev or simply <b>Pomin</b>. I am 20 years old. I am a 4th year student at the Gomel State Technical University (GSTU). I started learning programming in Pascal at school. Then at the university I began to study various programming languages, but settled on C#.
 </p>

### 🤝 Social media:
<div id="badges">
  <a href="https://vk.com/pxmiu">
    <img src="icons/VK.png" width="40" height="40" alt="vk" />
  </a>
  <a href="https://t.me/pxmiu">
    <img src="icons/Telegram.png" width="40" height="40" alt="telegram" />
  </a>
  <a href="https://www.instagram.com/99svd">
    <img src="icons/Instagram.png" width="40" height="40" alt="instagram" />
  </a>
  <a href="mailto:pmnsplay@gmail.com">
    <img src="icons/Gmail.png" width="40" height="40" alt="gmail" />
  </a>
</div>

### 🖥️ Technologies:
<img src="icons/dotnet.png" width="40" height="40" /><img src="icons/docker.png" width="40" height="40" />
<img src="icons/rabbitmq.svg" width="40" height="40" />
<img src="icons/Blazor.png" width="40" height="40" />
<img src="icons/mongodb.png" width="40" height="40" />
<img src="icons/sql-server.png" width="40" height="40" />
<img src="icons/postgresql.png" width="40" height="40" />
<img src="icons/mysql.png" width="40" height="40" />
<img src="icons/mediatr.png" width="40" height="40" />
<p>
  Databases:
  <ul>
    <li>MS SQL</li>
    <li>MySQL</li>
    <li>PostgreSQL</li>
    <li>SQLite</li>
    <li>MongoDB</li>
  </ul>
  Frontend:
  <ul>
    <li>WPF</li>
    <li>Window Forms</li>
    <li>Blazor</li>
    <li>Razor pages</li>
  </ul>
  Mappers:
  <ul>
    <li>AutoMapper</li>
    <li>Mapster</li>
    <li>Self mapper implemented by extension methods</li>
  </ul>
  ORMs:
  <ul>
    <li>Entity framework</li>
    <li>Dapper</li>
    <li>ADO.NET</li>
  </ul>
  Architecture:
  <ul>
    <li>Monolith</li>
    <li>3-layered</li>
    <li>Clean</li>
    <li>Microservices</li>
  </ul>
  Design patterns:
  <ul>
    <li>MVC</li>
    <li>MVVM</li>
  </ul>
  Testing:
  <ul>
    <li>xUnit</li>
    <li>NUnit</li>
  </ul>
  More:
  <ul>
    <li>MediatR</li>
    <li>RabbitMQ</li>
    <li>Docker</li>
    <li>Patterns</li>
    <li>Result type</li>
    <li>DDD</li>
    <li>FluentValidation</li>
    <li>NSubstitude</li>
    <li>WebAPI</li>
  </ul>
</p>

### 🛠 Instruments:
<img src="icons/visual-studio-code.png" width="40" height="40" /><img src="icons/visual-studio.png" width="40" height="40" />
<img src="icons/postman.png" width="40" height="40" />
<p>
  I use <b>Visual Studio</b> to solve problems. For editing files (JSON/XML, etc.) <b>Visual Studio Code</b>. To test API methods I use <b>Postman</b>.
</p>

### ⚙️ GitHub stats:

<table>
  <tr>
    <td>
      <img height="195px" align="right" alt="Github Languages" src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=TxkyoGhxul&layout=compact&theme=vision-friendly-dark" />
    </td>
    <td>
      <img src="https://github-readme-stats.vercel.app/api?username=TxkyoGhxul&show_icons=true&theme=merko" />
    </td>
  </tr>
</table>

---

## Русский 🇷🇺
### :man_technologist: Обо мне:
<p>
  Привет! Меня зовут Саша Поминдеев или просто <b>Помин</b>. Мне 20 лет. Я учусь на 4 курсе в Гомельском Государственном Техническом Университете (ГГТУ). Начал изучать программирование ещё в школе на Pascal. Далее в университете начал изучать различные языки программирования, но остановился на C#. 
 </p>

### 🤝 Социальные сети:
<div id="badges">
  <a href="https://vk.com/pxmiu">
    <img src="icons/VK.png" width="40" height="40" alt="vk" />
  </a>
  <a href="https://t.me/pxmiu">
    <img src="icons/Telegram.png" width="40" height="40" alt="telegram" />
  </a>
  <a href="https://www.instagram.com/99svd">
    <img src="icons/Instagram.png" width="40" height="40" alt="instagram" />
  </a>
  <a href="mailto:pmnsplay@gmail.com">
    <img src="icons/Gmail.png" width="40" height="40" alt="gmail" />
  </a>
</div>

### 🖥️ Технологии:
<img src="icons/dotnet.png" width="40" height="40" /><img src="icons/docker.png" width="40" height="40" />
<img src="icons/rabbitmq.svg" width="40" height="40" />
<img src="icons/Blazor.png" width="40" height="40" />
<img src="icons/mongodb.png" width="40" height="40" />
<img src="icons/sql-server.png" width="40" height="40" />
<img src="icons/postgresql.png" width="40" height="40" />
<img src="icons/mysql.png" width="40" height="40" />
<img src="icons/mediatr.png" width="40" height="40" />
<p>
  Базы данных:
  <ul>
    <li>MS SQL</li>
    <li>MySQL</li>
    <li>PostgreSQL</li>
    <li>SQLite</li>
    <li>MongoDB</li>
  </ul>
  Фронтенд:
  <ul>
    <li>WPF</li>
    <li>Window Forms</li>
    <li>Blazor</li>
    <li>Razor pages</li>
  </ul>
  Маппинг:
  <ul>
    <li>AutoMapper</li>
    <li>Mapster</li>
    <li>Собственный маппер через методы расширения</li>
  </ul>
  Доступ к данным:
  <ul>
    <li>Entity framework</li>
    <li>Dapper</li>
    <li>ADO.NET</li>
  </ul>
  Архитектуры:
  <ul>
    <li>Монолит</li>
    <li>Трехуровневая</li>
    <li>Чистая</li>
    <li>Микросервисная</li>
  </ul>
  Шаблоны проектирования:
  <ul>
    <li>MVC</li>
    <li>MVVM</li>
  </ul>
  Тестирование:
  <ul>
    <li>xUnit</li>
    <li>NUnit</li>
  </ul>
  Дополнительно:
  <ul>
    <li>MediatR</li>
    <li>RabbitMQ</li>
    <li>Docker</li>
    <li>Patterns</li>
    <li>Result type</li>
    <li>DDD</li>
    <li>FluentValidation</li>
    <li>NSubstitude</li>
    <li>WebAPI</li>
  </ul>
</p>

### 🛠 Инструменты:
<img src="icons/visual-studio-code.png" width="40" height="40" /><img src="icons/visual-studio.png" width="40" height="40" />
<img src="icons/postman.png" width="40" height="40" />
<p>
  Для решения задач использую <b>Visual Studio</b>. Для редактирования файлов (JSON/XML и др) <b>Visual Studio Code</b>. Для тестирования методов API использую <b>Postman</b>.
</p>

### ⚙️ GitHub статистика:

<table>
  <tr>
    <td>
      <img height="195px" align="right" alt="Github Languages" src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=TxkyoGhxul&layout=compact&theme=vision-friendly-dark" />
    </td>
    <td>
      <img src="https://github-readme-stats.vercel.app/api?username=TxkyoGhxul&show_icons=true&theme=merko" />
    </td>
  </tr>
</table>


---
