def insert_record_sequentially(filename, new_record, position):
 with open(filename, 'a') as file:
 lines = file.readlines()
 lines.insert(position, new_record + '\n')
 file.seek(0)
 file.writelines(lines)
def insert_record_randomly(filename, new_record, position, record_size):
 with open(filename, 'r+') as file:
 offset = position * record_size
 file.seek(offset)
 file.write(new_record + '\n')
 file.seek(0, 2)
 file.truncate()
filename = "my_file.txt"
new_record = "New record"
position = 2
record_size = 20
insert_record_sequentially(filename, new_record, position)
insert_record_randomly(filename, new_record, position, record_size)
