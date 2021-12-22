```
Base64加密文件与解密文件：

package com.example.demostudy.util.knownlege;

import org.apache.commons.codec.binary.Base64;
import org.apache.commons.io.FileUtils;

import java.io.File;
import java.io.IOException;

/**
 * @Description:
 * @Author: wangxb
 * @Datetime: 2021/11/18 18:42
 * @Version: 1.0
 */
public class BaseDecope {
    //编码
    public static String encodeFile(File file) throws IOException {
        byte[] readFileToByteArray = FileUtils.readFileToByteArray(file);
        return Base64.encodeBase64String(readFileToByteArray);
    }

    public static String encodeFile(String filePath) throws IOException {
        return encodeFile(new File(filePath));
    }
    //解码
    public static void decodeFile(String codes, File file) throws IOException {
        byte[] decodeBase64 = Base64.decodeBase64(codes);
        FileUtils.writeByteArrayToFile(file, decodeBase64);
    }
    public static void decodeFile(String codes, String filePath) throws IOException {
        decodeFile(codes, new File(filePath));
    }
}
```