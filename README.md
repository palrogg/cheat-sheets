A bit of everything - work in progress

NB use [this](https://github.com/palrogg/playfair-projects/tree/master/projects/paul-ronga) and [this](https://github.com/palrogg/foundations-homework/blob/master/README.md)

## Summary

1. [updates](#Updates) with npm, yarn, pip, homebrew, apt-get

2. [Python](#Python)
2.1 Pandas
2.2 Matplotlib
3. Shell
4. NodeJS
5. pm2
6. supervisor
7. nginx

# Updates
### Get version of version manager
`npm -v`
`pip show pip`

### Get version of package
`pip show *stuff*`
`npm view *stuff*`
`npm list *stuff*`
`yarn info *stuff*`

### Get versions of all packages
`npm list`
`pip freeze`

### Homebrew
`HOMEBREW_NO_AUTO_UPDATE=1 brew install`

# Python

## Pandas
### Time index
`pd.to_datetime(format='%...')`

`df.groupby(by=df.index.month).size()`

## Matplotlib

pdf

`matplotlib.rcParams['pdf.fonttype'] = 42`

### No spines
```
ax.spines['top'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.spines['left'].set_visible(False)
ax.spines['right'].set_visible(False)
```


### Small multiples
```
nrows = 4; ncols = 3
num_plots = nrows * ncols  # number of subplots
columns = ['temps s{}'.format(i) for i in range(2006, 2016)]

fig = plt.figure(figsize=(14, 10))

axes = [plt.subplot(nrows,ncols,i) for i in range(1,num_plots+1)]

plt.tight_layout(pad=0, w_pad=3, h_pad=1)
plt.subplots_adjust(hspace=.5)

colors = ['#FF2700', '#F6B900', '#77AB43', '#3EA8DC', 'red', 'orange', 'green', 'violet']

count = 0

for idx, runner in df_very_regulars.sort_values(by='time_evolution', ascending=True).iterrows():
    ax = axes[count]

    name = runner['nom']
    values = runner[columns].tolist()
    ax.plot(values)
    ax.set_title(name)

    ax.set_xlim([-.5, 9.5])
    ax.set_ylim([0, 2500])

    ax.set_xticks([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
    ax.set_xticklabels([2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015])
    count += 1
    if count >= num_plots:
        break

plt.savefig('stuff.pdf')
```

colors

## Shell

## NodeJS
