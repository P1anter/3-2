###과제1
힙 정렬(Heap sort) 구현

임의의 배열로부터 힙을 생성하는 코드 구현 (실행 1점, 오실행 0.5점, 미실행 0.2점)
생성된 힙으로부터 힙 정렬을 수행하는 코드 구현 (실행 1점, 오실행 0.5점, 미실행 0.2점)
Input : 아래와 같은 정렬이 되지 않은 1x20 배열
    [5, 10, 264, 362, 865, 63, 94, 475, 135, 932, 25, 9, 33, 287, 332, 745, 377, 820, 62, 1]

Output :
1. 1x20 입력 배열로부터 생성된 1x20 힙의 배열
2 . 정렬된 1x20 배열
       배열 포맷은 [a1, a2, …., a20]
---
제출
```python
def heapify(arr, n, i):
    """
    주어진 배열 arr의 i번째 인덱스를 루트로 하는 서브트리를 힙 속성이 유지되도록 재구성합니다.
    (최대 힙 기준)
    
    :param arr: 리스트 (배열)
    :param n: 힙의 크기
    :param i: 현재 힙을 재구성할 루트 인덱스
    """
    largest = i  # 현재 노드를 가장 큰 값으로 초기화
    left = 2 * i + 1  # 왼쪽 자식 노드 인덱스
    right = 2 * i + 2  # 오른쪽 자식 노드 인덱스

    # 왼쪽 자식 노드가 존재하고, 현재 가장 큰 값보다 크면 largest를 왼쪽 자식으로 변경
    if left < n and arr[i] < arr[left]:
        largest = left

    # 오른쪽 자식 노드가 존재하고, 현재 가장 큰 값보다 크면 largest를 오른쪽 자식으로 변경
    if right < n and arr[largest] < arr[right]:
        largest = right

    # largest가 원래 i가 아니면 (자식 노드가 더 크면)
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]  # 값 교환
        # 변경된 서브트리에 대해 재귀적으로 heapify 호출
        heapify(arr, n, largest)


def heap_sort(arr):
    """
    힙 정렬 알고리즘을 수행하여 배열을 오름차순으로 정렬합니다.
    
    :param arr: 정렬할 리스트 (배열)
    """
    n = len(arr)

    # 1. 힙 생성: 최대 힙을 만듭니다.
    # 배열의 마지막 부모 노드부터 시작하여 루트 노드까지 heapify를 호출합니다.
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # 힙 생성 후의 배열 (힙)을 출력합니다.
    print(f"1. 1x20 입력 배열로부터 생성된 1x20 힙의 배열:")
    print(f"[{', '.join(map(str, arr))}]")
    print("-" * 20)

    # 2. 힙 정렬: 힙에서 가장 큰 값을 하나씩 추출하여 정렬합니다.
    # 배열의 마지막 요소부터 시작하여 루트 노드까지 반복합니다.
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # 루트(가장 큰 값)와 마지막 값을 교환
        heapify(arr, i, 0)  # 교환 후, 줄어든 힙에서 다시 heapify를 호출하여 힙 속성 유지

    # 최종 정렬된 배열을 출력합니다.
    print(f"2. 정렬된 1x20 배열:")
    print(f"[{', '.join(map(str, arr))}]")


# 입력 배열
input_array = [5, 10, 264, 362, 865, 63, 94, 475, 135, 932, 25, 9, 33, 287, 332, 745, 377, 820, 62, 1]

# 힙 정렬 실행
heap_sort(input_array)
```
