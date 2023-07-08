using System;
using System.IO;

class Program
{
    static void Main()
    {
        string username = "YourUsername";
        string name = "Your Name";
        string skills = ".NET, C#, ASP.NET";
        string bio = "Passionate .NET developer with experience in building web applications.";

        string readmeContent = GenerateReadme(username, name, skills, bio);
        string readmeFilePath = "README.md";

        // Write the README content to a file
        File.WriteAllText(readmeFilePath, readmeContent);

        Console.WriteLine("README file generated successfully!");
    }

    static string GenerateReadme(string username, string name, string skills, string bio)
    {
        string readmeTemplate = @"
# Hi there, I'm {name}! 👋

## About Me

- 🔭 I’m currently working on {skills}
- 🌱 I’m currently learning new technologies and frameworks
- 👯 I’m looking to collaborate on open source projects
- 📫 How to reach me: [email](mailto:your-email@example.com)
- 😄 Pronouns: He/Him

## My GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username={username}&show_icons=true&count_private=true)

## Skills

- .NET
- C#
- ASP.NET

## Projects

- [Project 1](https://github.com/{username}/project1)
- [Project 2](https://github.com/{username}/project2)

## Contact Me

- LinkedIn: [Your LinkedIn Profile](https://www.linkedin.com/in/your-profile)
- Twitter: [@your-twitter-handle](https://twitter.com/your-twitter-handle)

";

        // Replace placeholders with actual values
        readmeTemplate = readmeTemplate.Replace("{username}", username);
        readmeTemplate = readmeTemplate.Replace("{name}", name);
        readmeTemplate = readmeTemplate.Replace("{skills}", skills);

        return readmeTemplate;
    }
}
