using System;

namespace WelcomeMessage
{
    class Program
    {
        static void Main(string[] args)
        {
            string linkdlnId = "linkedin.com/in/shraddha-bhure-989799218";
            string welcomeMessage = GenerateWelcomeMessage(linkdlnId);

            Console.WriteLine(welcomeMessage);
        }

        static string GenerateWelcomeMessage(string linkdlnId)
        {
            string[] parts = linkdlnId.Split('/');
            string lastPart = parts[parts.Length - 1];
            string[] nameParts = lastPart.Split('-');

            for (int i = 0; i < nameParts.Length; i++)
            {
                nameParts[i] = char.ToUpper(nameParts[i][0]) + nameParts[i].Substring(1);
            }

            string formattedName = string.Join("-", nameParts);

            return "Welcome to " + formattedName + "'s GitHub Profile";
        }
    }
}
