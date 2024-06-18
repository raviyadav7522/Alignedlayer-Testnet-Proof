# Alignedlayer Testnet Proof

root@vm1908062:~/Alignedlayer-Testnet-Proof# curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/install_aligned.sh | bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2230  100  2230    0     0  16840      0 --:--:-- --:--:-- --:--:-- 16893
Installing Aligned...
Aligned download successful, installing...
Aligned installed successfully in /root/.aligned/bin/aligned.

Detected your preferred shell is bash and added aligned to PATH.

Run 'source /root/.bashrc' or start a new terminal session to use aligned.

root@vm1908062:~/Alignedlayer-Testnet-Proof# source /root/.bashrc
root@vm1908062:~/Alignedlayer-Testnet-Proof# curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/get_proof_test_files.sh | bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1145  100  1145    0     0   3160      0 --:--:-- --:--:-- --:--:--  3162
Downloading SP1 ELF file...
SP1 ELF download successful
Downloading SP1 proof file...
SP1 proof downloaded successful
SP1 ELF and proof files downloaded successfully in /root/.aligned/test_files


root@vm1908062:~/Alignedlayer-Testnet-Proof# rm -rf ~/aligned_verification_data/ &&
aligned submit \
--proving_system SP1 \
--proof ~/.aligned/test_files/sp1_fibonacci.proof \
--vm_program ~/.aligned/test_files/sp1_fibonacci-elf \
--aligned_verification_data_path ~/aligned_verification_data \
--conn wss://batcher.alignedlayer.com
[2024-06-18T16:36:13Z INFO  aligned] WebSocket handshake has been successfully completed
[2024-06-18T16:36:13Z INFO  aligned] Message sent...
[2024-06-18T16:36:31Z INFO  aligned] Batcher response received:
    Batch inclusion response {
        ○ batch merkle root: 88f55b5895af2dbc493aaa02e242b1d143171a90d50b179d241a61e4c335dfa4
        ○ proof commitment: c181e470901eecf693bfa6f0e89e837dcf35700cdd91c210a0ce0660e8674208
    }
    
[2024-06-18T16:36:31Z INFO  aligned] Proof submitted to aligned. See the batch in the explorer:
    https://explorer.alignedlayer.com/batches/0x88f55b5895af2dbc493aaa02e242b1d143171a90d50b179d241a61e4c335dfa4

    
[2024-06-18T16:36:31Z INFO  aligned] Batch inclusion data written into /root/aligned_verification_data/88f55b5895af2dbc493aaa02e242b1d143171a90d50b179d241a61e4c335dfa4_186.json
[2024-06-18T16:36:31Z INFO  aligned] All messages responded. Closing connection...
root@vm1908062:~/Alignedlayer-Testnet-Proof#

