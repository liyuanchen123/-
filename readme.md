# This is a notebook of ML


test
percent_df = road.groupby(['道路名称','市','站点分类'])['站点分类'].apply(lambda x: x.count().max())/\
             road.groupby(['道路名称','市'])['站点分类'].apply(lambda x: x.count())

#将最数目最多的站点分类赋值为通道
for i,r in percent_final.iterrows():
    for k,val in maxdict.items():
        if k==i:
            for v in val:
                if r.values[0]==list(v.keys())[0]:
                    percent_final.loc[i,'通道'] = v[r.values[0]]
