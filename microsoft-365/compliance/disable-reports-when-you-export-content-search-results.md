---
title: コンテンツ検索の結果をエクスポートするときにレポートを無効にする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: ローカル コンピューター Windowsレジストリを編集して、コンテンツ検索の結果をローカル コンピューターからエクスポートするときにレポートを無効Microsoft 365 コンプライアンス センター。
ms.openlocfilehash: efe9ea768b68524dbfda003796a10d60453862bc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193160"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>コンテンツ検索の結果をエクスポートするときにレポートを無効にする

電子情報開示エクスポート ツールを使用して Microsoft 365 コンプライアンス センター でコンテンツ検索の結果をエクスポートすると、エクスポートされたコンテンツに関する追加情報を含む 2 つのレポートが自動的に作成およびエクスポートされます。 これらのレポートは、Results.csv ファイルと Manifest.xml ファイルです (これらのレポート[](#frequently-asked-questions-about-disabling-export-reports)の詳細については、このトピックの「エクスポート レポートの無効化に関するよく寄せられる質問」セクションを参照してください)。 これらのファイルは非常に大きいので、これらのファイルがエクスポートされるのを防ぐことで、ダウンロード時間を高速化し、ディスク領域を節約できます。 これを行うには、検索結果Windowsエクスポートするために使用するコンピューターのレジストリを変更します。 後でレポートを含める場合は、レジストリ設定を編集できます。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>エクスポート レポートを無効にするレジストリ設定を作成する

コンテンツ検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。
    
2. 無効にするエクスポート レポートに応じて、次の手順の 1 つまたは両方を実行します。
    
    - **Results.csv**
    
      ファイル名のサフィックス .reg をWindowsして、次のテキストをレジストリ ファイルに保存します。たとえば、DisableResultsCsv.reg などです。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      ファイル名のサフィックス .reg をWindowsして、次のテキストをレジストリ ファイルに保存します。たとえば、DisableManifestXml.reg などです。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. [Windows エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザー アクセス制御] ウィンドウで、[ **は** い] をクリックしてレジストリ エディターで変更を行います。 
    
5. 続行するように求めるメッセージが表示されたら、[はい] **をクリックします**。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>レジストリ設定を編集してエクスポート レポートを再び有効にする

前の手順で .reg ファイルを作成して Results.csv レポートと Manifest.xml レポートを無効にした場合は、それらのファイルを編集してレポートを再び有効にして、検索結果と一緒にエクスポートできます。 繰り返しになりますが、結果をコンテンツ検索のエクスポートに使用するコンピューターで、次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。
    
2. 前の手順で作成した .reg 編集ファイルの一方または両方を編集します。
    
    - **Results.csv**
    
        [DisableResultsCsv.reg] ファイルを開メモ帳に値を変更し、 `False` `True` ファイルを保存します。 たとえば、ファイルを編集すると、次のようになります。
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        次のコマンドで DisableManifestXml.reg ファイルを開メモ帳に値を変更し、 `False` `True` ファイルを保存します。 たとえば、ファイルを編集すると、次のようになります。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. [Windowsエクスプローラーで、前の手順で編集した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザー アクセス制御] ウィンドウで、[ **は** い] をクリックしてレジストリ エディターで変更を行います。 
    
5. 続行するように求めるメッセージが表示されたら、[はい] **をクリックします**。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>エクスポート レポートの無効化に関するよく寄せられる質問

 **レポートとResults.csvレポートManifest.xml。**
  
ファイルResults.csvおよびManifest.xmlファイルには、エクスポートされたコンテンツに関する追加情報が含まれている。
  
- **Results.csv** 検索結果Excelダウンロードされる各アイテムに関する情報を含むドキュメントを作成します。 電子メールの場合、結果ログには、次を含む各メッセージに関する情報が含まれます。 
    
  - 移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。
    
  - メッセージが送信または受信された日付。
    
  - メッセージの件名行。
    
  - メッセージの送信者と受信者。
    
  - 検索結果のエクスポート時に重複除外を有効にした場合、メッセージが重複メッセージかどうか。 重複メッセージには、メッセージを重複として識別する [ **親 ItemId]** 列の値が含まれます。 [親 **ItemId] 列の** 値は、エクスポートされたメッセージの **[アイテム ドキュメント Id]** 列の値と同じです。 
    
    サイトおよびサイトSharePoint OneDrive for Business、結果ログには、次を含む各ドキュメントに関する情報が含まれます。
    
  - ドキュメントの URL。
    
  - ドキュメントがあるサイト コレクションの URL。
    
  - ドキュメントが最後に変更された日付。
    
  - ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。
    
- **Manifest.xml** 検索結果に含まれる各アイテムに関する情報を含むマニフェスト ファイル (XML 形式)。 このレポートの情報は、Results.csvレポートと同じですが、電子探索参照モデル (EDRM) で指定された形式です。 EDRM の詳細については、 を参照してください [https://www.edrm.net](https://www.edrm.net) 。
    
 **これらのレポートのエクスポートを無効にすべきな場合**
  
特定のニーズに応じて異なります。 多くの組織は検索結果に関する追加情報を必要とし、これらのレポートを必要とします。
  
 **これを実行する必要があるコンピューターは何ですか?**
  
 電子情報開示エクスポート ツールを実行するローカル コンピューターのレジストリ設定を変更する必要があります。 
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか?**
  
いいえ、コンピューターを再起動する必要はありません。 ただし、電子情報開示エクスポート ツールが実行されている場合は、レジストリ設定を変更した後、電子情報開示エクスポート ツールを閉じてから再起動する必要があります。
  
 **既存のレジストリ キーが編集されるのか、新しいキーが作成されるのか。**
  
このトピックの手順で作成した .reg ファイルを初めて実行すると、新しいレジストリ キーが作成されます。 その後、.reg 編集ファイルを変更して再実行する度に設定が編集されます。
