---
title: 電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 電子情報開示検索結果をエクスポートするときに、コンピューターにダウンロードされる PST ファイルの既定のサイズを変更できます。
ms.openlocfilehash: 7c77edc4e565a76be41b274aac597c56780395d4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164118"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する

電子情報開示エクスポート ツールを使用して、さまざまな Microsoft 電子情報開示ツールから電子情報開示検索の電子メール結果をエクスポートする場合、エクスポートできる PST ファイルの既定のサイズは 10 GB です。 この既定のサイズを変更する場合は、検索結果のエクスポートに使用Windowsコンピューターのレジストリを編集できます。 これを行う理由の 1 つは、PST ファイルがリムーバブル メディア (DVD、コンパクト ディスク、USB ドライブなど) に収まる場合です。 
  
> [!NOTE]
> 電子情報開示のエクスポート ツールを使用して、コンテンツ検索ツールを使用して検索結果をエクスポートMicrosoft 365 コンプライアンス センター。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更するレジストリ設定を作成する

電子情報開示検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。 
    
2. ファイル名のサフィックス .reg を使用して、次のテキストを Window レジストリ ファイルに保存します。たとえば、PstExportSize.reg などです。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    上記の例では、値  `PstSizeLimitInBytes` は 1,073,741,824 バイトまたは約 1 GB に設定されています。 設定のその他のサンプル値を次に示  `PstSizeLimitInBytes` します。 
    
    |**GB 単位のサイズ (約)**|**バイト単位のサイズ**|
    |:-----|:-----|
    |0.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 検索結果をエクスポートするときに、PST ファイルの目的の最大サイズに値を変更し、 `PstSizeLimitInBytes` ファイルを保存します。 
    
4. [Windows エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
5. [ユーザー アクセス制御] ウィンドウで、[ **は** い] をクリックしてレジストリ エディターで変更を行います。 
    
6. 続行するように求めるメッセージが表示されたら、[はい] **をクリックします**。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
    
7. 手順 3 ~ 6 を繰り返して、レジストリ設定の値  `PstSizeLimitInBytes` を変更できます。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果のエクスポート時に PST ファイルの既定のサイズを変更する際によく寄せられる質問

 **既定のサイズが 10 GB である理由**
  
10 GB の既定のサイズは、顧客からのフィードバックに基づいて行いました。10 GB は、1 つの PST 内のコンテンツの最適な量と、ファイル破損の可能性が最小限に抑えた場合のバランスが良好です。
  
 **PST ファイルの既定のサイズを増減する必要がありますか?**
  
ユーザーは、組織内の他の場所に物理的に出荷できるリムーバブル メディアに検索結果が収まるサイズ制限を小さくする傾向があります。 PST ファイルが 10 GB を超える場合は破損の問題が発生する可能性があるため、既定のサイズを大きくすることをお勧めしません。
  
 **これを実行する必要があるコンピューターは何ですか?**
  
電子情報開示エクスポート ツールを実行するローカル コンピューターのレジストリ設定を変更する必要があります。
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか?**
  
いいえ、コンピューターを再起動する必要はありません。 ただし、電子情報開示エクスポート ツールが実行されている場合は、この設定を変更した後で、電子情報開示エクスポート ツールを閉じて再起動する必要があります。
  
 **既存のレジストリ キーが編集されるのか、新しいキーが作成されるのか。**
  
この手順で作成した .reg ファイルを初めて実行すると、新しいレジストリ キーが作成されます。 その後、.reg 編集ファイルを変更して再実行する度に設定が編集されます。
