# Yahan par aapko niche code milega


class Solution {
public:
pair<long long, long long> convert(string s) { long long integer = 0; string nonRep = "", rep = ""; int i = 0; while (i < s.size() && s[i] != '.') { integer = integer * 10 + (s[i] - '0'); i++; } if (i == s.size()) return {integer, 1}; i++; while (i < s.size() && s[i] != '(') {
nonRep += s[i]; i++; } if (i < s.size()) { i++; while (s[i] != ')') { rep += s[i]; i++; }} long long num = integer;
long long den = 1; if (!nonRep.empty()) { long long n = stoll(nonRep); long long d = pow(10, nonRep.size()); num = num * d + n; den *= d; } if (!rep.empty()) { long long r = stoll(rep); long long d = pow(10, rep.size()) - 1; long long shift = pow(10, nonRep.size()); num = num * d + r; den *= d; }
long long g = gcd(num, den); return {num / g, den / g}; } bool isRationalEqual(string s, string t) { return convert(s) == convert(t); }};
