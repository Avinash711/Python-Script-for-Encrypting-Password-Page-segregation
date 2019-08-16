##PassWord Encryption Script#

import PyPDF2 as pyp

pdfFile = open('sql - What is DDL and DML_ - Stack Overflow.pdf','rb')
pdfReader = pyp.PdfFileReader(pdfFile)
pdfWriter = pyp.PdfFileWriter()

for pageNum in range(pdfReader.numPages):
    pdfWriter.addPage(pdfReader.getPage(pageNum))
    
pdfWriter.encrypt('avinash11')
resultPdf = open('demo123.pdf','wb')
pdfWriter.write(resultPdf)
resultPdf.close()

##Script to retrive each pages in separate PDF formats##
from PyPDF2 import PdfFileWriter, PdfFileReader

pdf_in_file = open("Python django.pdf",'rb')

inputpdf = PdfFileReader(pdf_in_file)
pages_no = inputpdf.numPages

for i in range(pages_no):
    inputpdf = PdfFileReader(pdf_in_file)
    output = PdfFileWriter()
    output.addPage(inputpdf.getPage(i))
    with open("document-page%s.pdf" % i, "wb") as outputStream:
        output.write(outputStream)

pdf_in_file.close() 
