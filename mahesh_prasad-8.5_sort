import sys,csv
import operator

class MP_Sort:

	dl 		= 0
	
	dt 		= []
	
	def __init__(self):
		self.dt = []	

	def readCSV(self,file,de_limiter):
		try:
			self.dt = csv.reader(open(file),delimiter=de_limiter)
		except IOError as e:
			print "I/O error({0}): {1}".format(e.errno, e.strerror)
			raise
		except ValueError:
			print "Could not convert data to an integer."
			raise
		except:
			print "Unexpected error:", sys.exc_info()[0]
			raise	
			
	def readHD(self,dt):
		headerRow = dt.next()
		self.dl = len(headerRow)
		return headerRow
		
	def sortData(self,dt,by_index):
		sdt=[]
		try:
			sdt = sorted(dt, key=operator.itemgetter(by_index), reverse=True)	
		except IOError as e:
			print "I/O error({0}): {1}".format(e.errno, e.strerror)
			raise
		except ValueError:
			print "Could not convert data to an integer."
			raise
		except:
			print "Unexpected error:", sys.exc_info()[0]
			raise	
		return sdt
		
# end of MP_Sort class

# read a CSV file and do the functionality
mpSort = MP_Sort()		

# Read share prices CSV file
mpSort.readCSV('prices.csv',',')

headerRow = mpSort.readHD(mpSort.dt)

pdt = mpSort.dt;
# List for each Company year and month in which the share price was highest
# As CSV have 2 columns year and month so next column start with price data
# So 0 and 1 means years and months and from 2 means prices data
for n in range(2, mpSort.dl):
	print "Highest price of " + headerRow[n]
	pdt = mpSort.sortData(pdt,n)	
	if pdt!=[]:
		print pdt[0][0] + ' ' + pdt[0][1] + ' - ' + pdt[0][n]	
		
