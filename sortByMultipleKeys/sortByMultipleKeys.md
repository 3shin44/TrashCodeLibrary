# Sort objects in array by two keys
排序陣列中的物件，依據物件的Key值進行排序，規則為：
先以類別 (Type)，排序後再依編碼 (id)排序

## Input/Output

### input
```
[
{Type: "AA", id:3},
{Type: "BB", id:1},
{Type: "AA", id:1},
{Type: "AA", id:4},
{Type: "AA", id:6},
{Type: "BB", id:3}
]
```

### Output
```
[
{Type: "AA", id: 1},
{Type: "AA", id: 3},
{Type: "AA", id: 4},
{Type: "AA", id: 6},
{Type: "BB", id: 1},
{Type: "BB", id: 3}
]
```

### Code
```
  /*
   * JS 陣列中物件依照 排序依據 firstKey(字串), 若firstKey相同則依據 sencondKey(字串) 排序
   * sourceArray - 原始陣列
   * firstKey - 排序規則1 key值(string)
   * sencondKey - 排序規則2 key值(string)
   * return 轉換後已排序陣列
   */
  function sortByTypeAndID(sourceArray = [], firstKey = "", sencondKey = "") {
    sourceArray.sort(function (a, b) {
      if (a[firstKey] == b[firstKey]) {
        return a[sencondKey].toString() > b[sencondKey].toString() ? 1 : -1;
      } else {
        return a[firstKey].toString() > b[firstKey].toString() ? 1 : -1;
      }
    });
    return sourceArray;
  }
```

## Demo
```
let arr = [
{Type: "AA", id:3},
{Type: "BB", id:1},
{Type: "AA", id:1},
{Type: "AA", id:4},
{Type: "AA", id:6},
{Type: "BB", id:3}
];

function sortByTypeAndID(sourceArray = [], firstKey = "", sencondKey = "") {
	sourceArray.sort(function (a, b) {
	  if (a[firstKey] == b[firstKey]) {
		return a[sencondKey].toString() > b[sencondKey].toString() ? 1 : -1;
	  } else {
		return a[firstKey].toString() > b[firstKey].toString() ? 1 : -1;
	  }
	});
	return sourceArray;
}

sortByTypeAndID(arr, "Type", "id");
```