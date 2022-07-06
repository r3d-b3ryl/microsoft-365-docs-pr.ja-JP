---
title: 電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 電子情報開示検索結果をエクスポートするときに、コンピューターにダウンロードされる PST ファイルの既定のサイズを変更できます。
ms.openlocfilehash: e2387f403854561c9906f252ad39be740c62ae19
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638788"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する

電子情報開示エクスポート ツールを使用して、さまざまな Microsoft 電子情報開示ツールから電子情報開示検索の電子メール結果をエクスポートする場合、エクスポートできる PST ファイルの既定のサイズは 10 GB です。 この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターで Windows レジストリを編集できます。 これを行う理由の 1 つは、PST ファイルがリムーバブル メディア (DVD、コンパクト ディスク、USB ドライブなど) に収まるようにするためです。 
  
> [!NOTE]
> 電子情報開示エクスポート ツールは、Microsoft Purview コンプライアンス ポータルのコンテンツ検索ツールを使用するときに検索結果をエクスポートするために使用されます。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更するレジストリ設定を作成する

電子情報開示検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。 
    
2. .reg のファイル名サフィックスを使用して、次のテキストを Window レジストリ ファイルに保存します。たとえば、PstExportSize.reg です。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    上の例では、  `PstSizeLimitInBytes` 値は 1,073,741,824 バイトまたは約 1 GB に設定されています。 設定のその他のサンプル値を次に示します  `PstSizeLimitInBytes` 。 
    
    |**サイズ (GB 単位) (約)**|**サイズ (バイト単位)**|
    |:-----|:-----|
    |0.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 検索結果を `PstSizeLimitInBytes` エクスポートするときに、PST ファイルの目的の最大サイズに値を変更し、ファイルを保存します。 
    
4. Windows エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
5. [ユーザー Access Control] ウィンドウで 、[**はい**] をクリックしてレジストリ エディターに変更を加えます。 
    
6. 続行するように求められたら、[ **はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
    
7. 手順 3 ~ 6 を繰り返して、レジストリ設定の値を  `PstSizeLimitInBytes` 変更できます。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルの既定のサイズを変更する方法についてよく寄せられる質問

 **既定のサイズが 10 GB である理由**
  
10 GB の既定のサイズは、顧客からのフィードバックに基づいていました。10 GB は、1 つの PST 内のコンテンツの最適な量と、ファイルの破損の可能性を最小限に抑えるのに適したバランスです。
  
 **PST ファイルの既定のサイズを増減する必要がありますか?**
  
顧客は、組織内の他の場所に物理的に発送できるリムーバブル メディアに検索結果が収まるように、サイズ制限を小さくする傾向があります。 10 GB を超える PST ファイルでは破損の問題が発生する可能性があるため、既定のサイズを大きくすることはお勧めしません。
  
 **これを行う必要があるコンピューターは何ですか?**
  
電子情報開示エクスポート ツールを実行するローカル コンピューターでレジストリ設定を変更する必要があります。
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか?**
  
いいえ。コンピューターを再起動する必要はありません。 ただし、電子情報開示エクスポート ツールが実行されている場合は、この設定を変更した後、それを閉じて再起動する必要があります。
  
 **既存のレジストリ キーは編集されるか、新しいキーが作成されますか?**
  
この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリ キーが作成されます。 その後、.reg 編集ファイルを変更して再実行するたびに設定が編集されます。
