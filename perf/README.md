Performance Tests


Please find the below steps for running the Stress Test
Client : 10.0.15.105 , Server : 10.0.15.105 ,GW :10.0.28.110 ,HA :10.0.51.136

Remove the old logs from GW and continue the below steps in sequence(first wpg server then client)

a,Login to WPG server:(10.0.15.60)
ssh xxx@10.0.15.60
execute the below command
sudo /home/tejaswi.chunduri/server-4.9.0 --config clt_1domain_300robots_1con.pg  --log logs/srv1_20170614POST5KR1.log --verb_lvl 10 --accept_foreign_msgs yes --ign_urls yes

b,Login to WPG server:(10.0.15.105)
ssh xxx@10.0.15.105
execute the below command
sudo /home/tejaswi.chunduri/client-4.9.0 --config clt_1domain_300robots_1con.pg --proxy 10.0.51.136:443 --log logs/clt_20170614POST5KR1.log --verb_lvl 10

