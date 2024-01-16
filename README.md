# Membuat-CRUD-Peminjaman-Buku-Perpustakaan
Membuat CRUD Peminjaman Buku Perpustakaan

-- membuat database dan table
CREATE DATABASE db_perpustakaan

CREATE TABLE `account` (
  `id` INT(11) NOT NULL,
  `username` VARCHAR(255) NOT NULL,
  `fullname` VARCHAR(255) NOT NULL,
  `email` VARCHAR(255) NOT NULL,
  `password` VARCHAR(255) NOT NULL
) 

SELECT * FROM ACCOUNT

INSERT INTO `account` (`id`, `username`, `fullname`, `email`, `password`) VALUES
(1, 'Rizal', 'Rizal Ainun Yaqin', 'rizalyaqin8@gmail.com', '12345'),
(18, 'Ainun', 'Habibi Ainun', 'ainun@gmail.com', '11111');


CREATE TABLE `book` (
  `id` INT(11) NOT NULL,
  `title` VARCHAR(255) NOT NULL,
  `author` VARCHAR(255) NOT NULL,
  `publisher` VARCHAR(255) NOT NULL,
  `amount` INT(11) NOT NULL,
  `photo_filename` VARCHAR(255) DEFAULT NULL
) 

INSERT INTO `book` (`id`, `title`, `author`, `publisher`, `amount`, `photo_filename`) VALUES
(1, 'Humor Informatika', 'Ariwibowo', 'Republika', 5, 'Humor Informatika_20231226_084031.jpg'),
(2, 'Laskar Pelangi', 'Andrea Hirata', 'Bentang Pustaka', 14, 'Laskar Pelangi_20231226_083807.png')

SELECT * FROM book


CREATE TABLE `borrowing` (
  `id` INT(11) NOT NULL,
  `borrower_id` INT(11) NOT NULL,
  `book_id` INT(11) NOT NULL,
  `loan_date` DATE NOT NULL,
  `return_date` DATE NOT NULL,
  `status` VARCHAR(255) NOT NULL
) 

SELECT * FROM borrowing
INSERT INTO `borrowing` (`id`, `borrower_id`, `book_id`, `loan_date`, `return_date`, `status`) VALUES
(15, 2, 2, '2023-12-01', '2023-12-06', 'Belum Kembali'),
(17, 1, 5, '2023-12-22', '2023-12-29', 'Sudah Kembali'),
(18, 7, 1, '2023-12-22', '2023-12-29', 'Sudah Kembali'),
(19, 3, 5, '2023-12-22', '2023-12-29', 'Sudah Kembali'),
(20, 5, 3, '2023-12-26', '2024-01-02', 'Belum Kembali'),
(21, 4, 3, '2023-12-27', '2024-01-03', 'Belum Kembali');


CREATE TABLE `member` (
  `id` INT(11) NOT NULL,
  `fullname` VARCHAR(255) NOT NULL,
  `address` VARCHAR(255) NOT NULL,
  `phone_number` VARCHAR(15) NOT NULL,
  `gender` VARCHAR(20) NOT NULL,
  `photo_filename` VARCHAR(255) DEFAULT NULL
) 

INSERT INTO `member` (`id`, `fullname`, `address`, `phone_number`, `gender`, `photo_filename`) VALUES
(1, 'Rizal Ainun Yaqin', 'Jalan Raya Srandakan Km.1 Trimurti, Srandakan Bantul 55762 Daerah Istimewa Yogyakarta.', '+628523678921', 'laki-laki', 'Rizal Ainun Yaqin_20240103_152800.png'),


ALTER TABLE `account`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `book`
--
ALTER TABLE `book`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `borrowing`
--
ALTER TABLE `borrowing`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `borrower_id` (`borrower_id`,`book_id`),
  ADD KEY `book_id` (`book_id`);

--
-- Indexes for table `member`
--
ALTER TABLE `member`
  ADD PRIMARY KEY (`id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `account`
--
ALTER TABLE `account`
  MODIFY `id` INT(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=19;

--
-- AUTO_INCREMENT for table `book`
--
ALTER TABLE `book`
  MODIFY `id` INT(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=19;

--
-- AUTO_INCREMENT for table `borrowing`
--
ALTER TABLE `borrowing`
  MODIFY `id` INT(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=22;

--
-- AUTO_INCREMENT for table `member`
--
ALTER TABLE `member`
  MODIFY `id` INT(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=21;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `borrowing`
--
ALTER TABLE `borrowing`
  ADD CONSTRAINT `borrowing_ibfk_1` FOREIGN KEY (`borrower_id`) REFERENCES `member` (`id`),
  ADD CONSTRAINT `borrowing_ibfk_2` FOREIGN KEY (`book_id`) REFERENCES `book` (`id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
MDESCRIPTION,MARK) VALUES (@userId,'ReportPembelian','laporan Pembelian',0)


CREATE VIEW vUsers AS
SELECT a.iduser,a.username,a.password,b.formname,b.mark,b.formdescription
FROM users A INNER JOIN USERSFORM b ON A.iduser = b.IDUSER

SELECT * FROM USERSFORM
