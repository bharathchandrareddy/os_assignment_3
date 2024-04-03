# os_assignment_3
operating systems assignment 3

Memory Management: Logical to Physical Address Translation
This Python script demonstrates the fundamentals of memory management by translating logical addresses to physical addresses using a predefined page/frame table. It is divided into several key parts, each handling a specific aspect of the address translation process. The script includes defining a page/frame table, translating logical addresses to physical addresses, and extracting page numbers and offsets from logical addresses.

Overview
The script is structured into three main parts:

Define a Page/Frame Table
Translate Logical Addresses to Physical Addresses
Provide Page Numbers and Offset for Given Logical Addresses
Below is an explanation of each part:

1. Define a Page/Frame Table
This section initializes a page_frame_table dictionary to represent the mapping of logical page numbers to physical frame numbers. Each entry in the table maps a logical page number (the key) to a corresponding physical frame number (the value).

Example mappings included in the script:

python
Copy code
page_frame_table = {
    0x01: 0x05,
    0x02: 0x0A,
    0x03: 0x03,
    0x04: 0x09,
    0x05: 0x04,
}
This table is crucial for the address translation process, as it allows the program to find the physical frame number associated with a given logical page number.

2. Translate Logical Addresses to Physical Addresses
In this part, a function translate_logical_to_physical is defined to translate a logical address into a physical address. The function extracts the page number and offset from the given logical address. Using the page number, it looks up the corresponding frame number from the page_frame_table. If the page number is found, it combines the frame number with the offset to generate the physical address.

If the page number does not exist in the table (simulating a page fault), the function returns an error message indicating the page fault.

3. Provide Page Numbers and Offset for Given Logical Addresses
This section includes a function get_page_number_and_offset that takes a list of logical addresses as input. For each address, it extracts and prints the page number and offset. This function demonstrates how logical addresses are decomposed into their constituent parts, which is a foundational concept in memory management.

The script concludes by displaying the page numbers and offsets for a sample set of logical addresses and attempting to translate those addresses using the previously defined functions.

Sample Input and Output
The script processes a sample list of logical addresses:

python
Copy code
logical_addresses = [0x3A7F, 0xABCD, 0x5678]
For each address, it provides the page number and offset, and attempts to translate it to a physical address using the predefined page/frame table.

Conclusion
This script offers a basic but illustrative example of memory management techniques, specifically the translation of logical addresses to physical addresses using a page/frame table. It is intended for educational purposes, to help students understand the concepts of paging, logical and physical address space, and the handling of page faults
