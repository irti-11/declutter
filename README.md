# Declutter

<img width="937" height="478" alt="image" src="https://github.com/user-attachments/assets/989610a3-4e74-4e24-8537-1316f7703fe5" />


A local only file sorter that runs entirely in your browser. Pick a messy folder, and it groups every file into folders based on its extension. No uploads, no server, no account. Your files never leave your device.

## Why I built this

I had a folder full of random files. Images, PDFs, docs, all mixed together with no structure. Finding anything took forever, and sorting hundreds of files one by one was not something I wanted to spend my evening on.

The first version of this idea was a small Node.js script. It read each file's extension, made a folder for that type if it did not exist yet, and moved the file in. Simple logic, but it saved me a lot of time. I liked the idea so much that I decided to build it into a full website, so anyone could use it without touching the terminal.

That website became Declutter.

## What it does

1. You select a folder on your computer.
2. It scans every file inside that folder.
3. It groups the files by their extension (jpg, pdf, docx, and so on).
4. It creates a folder for each type and moves the matching files in.
5. You get a live log showing what moved where, plus a progress bar.

Everything happens on your machine using the browser's File System Access API. Nothing is uploaded anywhere, and there is no backend involved.

## Features

- **Local only.** Files are read and moved directly on your device. Nothing is sent to a server.
- **Undo support.** Every sort is logged during the session, so you can revert it with one click if you change your mind.
- **Manifest export.** Download a JSON file that records exactly what was moved. You can load it later to revert a sort, even after closing the tab or restarting your browser.
- **Duplicate handling.** If a file with the same name already exists in the destination folder, it automatically renames the new one instead of overwriting it.
- **Light and dark themes**, saved automatically for your next visit.

## How to use it

1. Open the app in a Chromium based browser (Chrome, Edge, or Brave). The File System Access API is not supported in Firefox or Safari yet.
2. Click the button to pick a folder.
3. Review the scan results. You will see how many files of each type were found.
4. Choose which extensions you want sorted, if you do not want to sort everything at once.
5. Click sort. The app creates folders and moves the files in.
6. If something goes wrong or you change your mind, use the revert button, or load a previously downloaded manifest to undo it later.

## Tech used

- Vanilla JavaScript, no frameworks
- File System Access API for reading and writing files locally
- Plain HTML and CSS, with CSS variables for theming

## Common questions

**Does this upload my files anywhere?**
No. Everything happens locally in your browser using the File System Access API. There is no server involved, and no network request is made with your file data.

**Why does the folder picker not show up on my browser?**
The File System Access API currently only works in Chromium based browsers like Chrome, Edge, and Brave. Firefox and Safari do not support it yet.

**What happens if I sort the wrong files?**
Click the revert button right after sorting to move everything back. If you already closed the tab, download the manifest before you sort next time, so you always have a way to undo it later.

**Will it overwrite files with the same name?**
No. If a file with the same name already exists in the destination folder, Declutter automatically renames the incoming file instead of overwriting anything.

**Can I use this on a huge folder with thousands of files?**
Yes, it processes files concurrently in small batches, so it stays responsive even with a large number of files.

## Project background

This started as a small Node.js script built to solve a personal problem, then grew into a full browser based tool. It is a good example of taking a simple piece of logic and turning it into something other people can actually use, without needing to install anything or run a single command.

## License

Feel free to use, modify, or learn from this project.
