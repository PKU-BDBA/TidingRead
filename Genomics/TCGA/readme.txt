** 清洗数据说明 **

cli_short.txt
	清洗后的临床数据
	字段说明：tumor_tissue_site, 肿瘤来源; gender, 性别; age_at_initial_pathologic_diagnosis, 年龄; cancer, 1-cancer 0-health（该文件中没有只有在match过的cli文件里才有该字段，因为每个病人有多个样本，包括肿瘤组织和癌旁正常组织等，只有到样本级别才会有是否是肿瘤的信息）; 

meth_beta_dat.txt	
	清洗后的甲基化数据，非常大~80G，~12k*450K的矩阵，第一列为file_id
meth_idmap.txt
	各种ID之间的匹配, 每一个原始数据都有自己唯一的file_id，同一个患者有相同的pts_id，同一个样本有相同的samp_id1（不是samp_id），file_path为原始数据绝对路径；
	临床信息通过pts_id匹配cli_XXX文件；不同实验之间通过samp_id1匹配；
	由于整理后的文件太大，读写有限制，可能需要从原始数据读取；

rnaseq_expr_dat.txt
	清洗后的表达谱数据，~8G，~18k*60k的矩阵，第一列file_id
rnaseq_idmap.txt
	同上


XXX.match-rd.txt
	这部分文件是对RNA-Seq 和DNA-Methy数据匹配后整理出来的文件, 行（样本）已经对齐； 甲基化数据由于太大，暂时未做处理


** 原始数据说明 **

XXX_gene_counts.tsv
	表达量数据，第一行为注释信息，第二行为表头，第三到六行为统计信息，需要第一列gene_id和第七列tpm_xxx（标准化之后的表达量）

XXX_level3betas.txt
	甲基化数据，只有两列，第一列为探针编号，第二列为甲基化水平，无表头
	
