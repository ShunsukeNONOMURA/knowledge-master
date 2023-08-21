# knowledge master
knowledge構築dockerファイル一式

## 稼働管理
シンプルにdocker composeで良い
```
docker compose up -d
docker compose down
```

## バックアップ手順
volumesを差し替えれば復旧することが可能なので、このディレクトリを複製する。
```
docker compose down
sudo chmod 777 -R volumes/
cp -r volumes ./buckups/volumes_`date +%Y%m%d`
docker compose up
```

### 備考
- volumes/postgresql 以下でうまく保存できないので、所有権を変えている