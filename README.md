// 1)დაწერეთ ფუნქცია რომელიც მიღებული რიცხვების მასივიდან
//   დააბრუნებს უდიდეს ელემენტს

function getMaxNumberArray(numbersArray) {
  return Math.max(...numbersArray);
}

// 2)დაწერეტ ფუნქცია რომელიც ღებულობს რიცხვენის მასივს და ანრუნებს
//   დადებითი რიცხვების საშუალო მნიშვნელობას. (მაგალითად თუ გადაეცემა მასივი [-1, 2, 4] უნდა დააბრუნოს 3: (4 + 2) / 2)

function getPositiveNumbersAverage(numbersArray) {
  const positiveNumbersArray = numbersArray.filter((number) => {
    return number > 0;
  });

  const positiveNumbersSum = positiveNumbersArray.reduce((acc, number) => {
    return acc + number;
  }, 0);

  return positiveNumbersSum / positiveNumbersArray.length;
}

// დაწერეთ ფუნქცია რომელიც ღებულობს სტუდენტების 2 მასივს
// (თითო სტუდენტი წარმოდგენილია ობიექტით შემდეგი ველებით {id: number, name: string, gpa: number}) და დააბრუნებს უდიდესი gpa-ს მქონე 5 სტუდენტს მასივის სახით. თუ რამდენიმე სტუდენტი არის ერთნაირი
// gpa-თი და შედის ტოპ 5 gpa-ებში უნდა დააბრუნოს ყველა ასეთი სტუდენტი (მაგალითად თუ სტუდენტებს შემდეგი gpa აქვთ: [2, 2, 3.5, 3.5 4, 4, 4, 4] ფუნქციამ უნდა დააბრუნოს შემდეგი gpa-ს მქონე სტუდენტი:
// [3.5, 3.5 4, 4, 4, 4] მიუხედავად იმსია რომ 5-ზე მეტი იქნება)

// interface Student {
//   id: number;
//   name: String;
//   gpa: number
// }

function getTopStudents(studentsArray1, studentsArray2) {
  const mergedArrays = [...studentsArray1, ...studentsArray2];

  const sortedStudents = mergedArrays.sort((student1, student2) => {
    return student2.gpa - student1.gpa;
  });

  while (sortedStudents.length > 5) {
    sortedStudents.pop();
  }

  return sortedStudents;
}

// [
//   { id: 1, name: "boris", gpa: 4 },
//   { id: 2, name: "nika", gpa: 2 },
//   { id: 1, name: "bumeranga", gpa: 1 },
// ];
// [
//   { id: 1, name: "genadi", gpa: 3.5 },
//   { id: 2, name: "spiridoni", gpa: 2.5 },
//   { id: 1, name: "nostradamusi", gpa: 0.3 },
// ];
getTopStudents();