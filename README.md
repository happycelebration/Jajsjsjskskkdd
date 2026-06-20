# Yahan par aapko niche code milega


class Solution {
public:
 int findPeak(MountainArray &mountainArr) {
int l = 0; int r = mountainArr.length() - 1; while (l < r) { int mid = l + (r - l) / 2;nif (mountainArr.get(mid) < mountainArr.get(mid + 1)) l = mid + 1; else r = mid; } return l; } int binarySearchAsc(MountainArray &mountainArr,
 int l, int r, int target) { while (l <= r) { int mid = l + (r - l) / 2; int val = mountainArr.get(mid); if (val == target) return mid; if (val < target) l = mid + 1; else
 r = mid - 1; } return -1; } int binarySearchDesc(MountainArray &mountainArr,
 int l, int r, int target) { while (l <= r) { int mid = l + (r - l) / 2; int val = mountainArr.get(mid); if (val == target) return mid; if (val > target) l = mid + 1; else
 r = mid - 1; } return -1; } int findInMountainArray(int target, MountainArray &mountainArr) { int peak = findPeak(mountainArr);
int left = binarySearchAsc( mountainArr, 0, peak, target ); if (left != -1) return left; return binarySearchDesc( mountainArr, peak + 1,
mountainArr.length() - 1, target );}};
