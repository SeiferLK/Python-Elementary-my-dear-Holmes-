Professor Moriarty is causing trouble again! Mary managed to get a file with a piece of his plan, but it's encoded. Before she could decode it, Moriarty had taken her hostage and Dr. Watson went to the rescue.

Holmes anticipated that and found a simple Caesar cipher decoder on Stack Overflow to deal with it himself. Initially, the file Holmes got from Mary was called "13.txt", so he presupposed that this might be the offset n. Check this theory but keep in mind that for decoding the offset has to be taken with a minus:

def decode_Caesar_cipher(s, n):
    alpha = " ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz',.?!"
    s = s.strip()
    text = ''
    for c in s:
        text += alpha[(alpha.index(c) + n) % len(alpha)]
    print('Decoded text: "' + text + '"')

Holmes, however, doesn't know how to work with files, so you must help him! You will be given the file Mary got from Moriarty's laptop. Using the code Holmes found, write a program that takes a file as an argument, reads it, decodes it, and prints the decoded text. Even though the provided piece of code above contains the phrase "Decoded text: " and quotes, please output only the decoded text itself.

If your argument --file is stored in the variable args, you can read the file you've passed to your script this way:

filename = args.file
opened_file = open(filename)
encoded_text = opened_file.read()  # read the file into a string
opened_file.close()  # always close the files you've opened
