This repository allows to reproduce angular bug ""ng serve" doesn't react on changes in d.ts files."


### Description
"ng serve" doesn't react on changes in d.ts files.

## 🔬 Minimal Reproduction
### Precondition:
1. Clone repository: https://github.com/VlasovSergey/angular-ng-serbe-ignores-dts.git
2. run `npm install`
3. run `ng serve`
4. comment `func: () => void;` in file `src\typings.ts`
*Expected:*  'ng serve' runs build and shows an error because `module.ts` uses function func.
*Actual:* 'ng serve' do nothing.

5. re-run `ng serve` (it shows error).
6. make any change in main.ts but don't fix the error (`ng serve` rebuild project and show error correctly)
7. uncomment `func: () => void;` in file `src\typings.ts`

*Expected:* `ng serve` rebuilds the project and the error disappears.
*Actual:* 'ng serve' do nothing. Moreover, if I trigger `ng serve` again (by changing main.ts) the error will be still here.
    