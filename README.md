# Yahan par aapko niche code milega


class Solution {
public:
int findInMountainArray(int target, MountainArray& mountainArr) { int n=mountainArr.length(),peak=peakIndex(mountainArr,0,n-1),left=searchLeft(mountainArr,target,0,peak);
 if(mountainArr.get(left)==target) return left;
 int right=searchRight(mountainArr,target,peak+1,n-1); if(mountainArr.get(right)==target) return right; return -1; } int peakIndex(MountainArray& A,int l,int r){ while(l<r){
 int m=(l+r)/2; if(A.get(m)<A.get(m+1)) l=m+1; else r=m; } return l; } int searchLeft(MountainArray& A,int target,int l,int r){
while(l<r){ int m=(l+r)/2; if(A.get(m)<target) l=m+1;
else r=m; } return l; } int searchRight(MountainArray& A,int target,int l,int r){
while(l<r){ int m=(l+r)/2; if(A.get(m)>target) l=m+1; else r=m; } return l; }};
