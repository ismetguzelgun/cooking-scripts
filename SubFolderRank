using System;
using System.IO;


namespace SubFolderRank
{
    class Program
    {
        static void Main(string[] args)
        {
            string path = @"D:\MainFolder";
            string destination = @"D:\NewwFolder";
            RenameFiles(path, destination);
            MoveToFolder(path, destination);
            //ReadEx(destination);
            Console.ReadLine();
        }

        private static void MoveToFolder(string path, string destination)
        {
            DirectoryInfo di = new DirectoryInfo(path);

            foreach (DirectoryInfo si in di.GetDirectories("*", SearchOption.TopDirectoryOnly))
            {
                foreach (FileInfo fi in si.GetFiles())
                {
                    string fullSourcePath = Path.Combine(path, si.Name + "\\" + fi.Name);
                    string fullDestPath = Path.Combine(destination, si.Name + "\\" + fi.Name);

                    File.Move(fullSourcePath, destination + "\\" + fi.Name);

                    //File.Move(fullSourcePath, fullDestPath);

                    //File.Copy (fi.FullName, destination);
                }
            }
            Console.WriteLine("Moved");
        }

        private static void RenameFiles(string path, string destination)
        {
            //Console.WriteLine("{0} {1} {2}", path, source, dest); 

            DirectoryInfo di = new DirectoryInfo(path);

            foreach (DirectoryInfo si in di.GetDirectories("*", SearchOption.TopDirectoryOnly))
            {
                foreach (FileInfo fi in si.GetFiles())
                {
                    //fi.Name = si.Name;
                    if (fi.FullName != Path.Combine(fi.DirectoryName, si.Name + fi.Name))
                        File.Move(fi.FullName, Path.Combine(fi.DirectoryName, si.Name + fi.Name));

                }
            }
            Console.WriteLine("Renamed");
        }

    }
}

