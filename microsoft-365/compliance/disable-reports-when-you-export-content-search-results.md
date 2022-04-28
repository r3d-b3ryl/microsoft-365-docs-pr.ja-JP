---
title: コンテンツ検索の結果をエクスポートするときにレポートを無効にする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Microsoft Purview コンプライアンス ポータルからコンテンツ検索の結果をエクスポートするときに、ローカル コンピューターの Windows レジストリを編集してレポートを無効にします。
ms.openlocfilehash: 3f44c30b2fe3459e44f2d1c5a2d372e57774eeb2
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094970"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>コンテンツ検索の結果をエクスポートするときにレポートを無効にする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

電子情報開示エクスポート ツールを使用して Microsoft Purview コンプライアンス ポータルでコンテンツ検索の結果をエクスポートすると、エクスポートされたコンテンツに関する追加情報を含む 2 つのレポートが自動的に作成およびエクスポートされます。 これらのレポートは、Results.csv ファイルとManifest.xml ファイルです (これらのレポートの詳細については、このトピックの [「エクスポート レポートの無効化に関するよく寄せられる質問](#frequently-asked-questions-about-disabling-export-reports) 」セクションを参照してください)。 これらのファイルは非常に大きくなる可能性があるため、これらのファイルがエクスポートされないようにすることで、ダウンロード時間を短縮し、ディスク領域を節約できます。 これを行うには、検索結果のエクスポートに使用するコンピューターの Windows レジストリを変更します。 後でレポートを含める場合は、レジストリ設定を編集できます。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>エクスポート レポートを無効にするレジストリ設定を作成する

コンテンツ検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。
    
2. 無効にするエクスポート レポートに応じて、次の手順のいずれかまたは両方を実行します。
    
    - **Results.csv**
    
      次のテキストを .reg のファイル名サフィックス (DisableResultsCsv.reg など) を使用して、Windows レジストリ ファイルに保存します。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      次のテキストを .reg のファイル名サフィックス (DisableManifestXml.reg など) を使用して、Windows レジストリ ファイルに保存します。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Windows エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザー Access Control] ウィンドウで 、[**はい**] をクリックしてレジストリ エディターに変更を加えます。 
    
5. 続行するように求められたら、[ **はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>レジストリ設定を編集してエクスポート レポートを再度有効にする

前の手順で .reg ファイルを作成してResults.csvレポートとManifest.xml レポートを無効にした場合は、それらのファイルを編集して、検索結果と共にエクスポートされるようにレポートを再度有効にすることができます。 ここでも、コンテンツ検索の結果をエクスポートするために使用するコンピューターで次の手順を実行します。
  
1. 開いている場合は、電子情報開示エクスポート ツールを閉じます。
    
2. 前の手順で作成した .reg 編集ファイルの 1 つまたは両方を編集します。
    
    - **Results.csv**
    
        メモ帳で DisableResultsCsv.reg ファイルを開き、値`False`を変更`True`してファイルを保存します。 たとえば、ファイルを編集すると、次のようになります。
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        メモ帳で DisableManifestXml.reg ファイルを開き、値`False`を変更`True`してファイルを保存します。 たとえば、ファイルを編集すると、次のようになります。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Windows エクスプローラーで、前の手順で編集した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザー Access Control] ウィンドウで 、[**はい**] をクリックしてレジストリ エディターに変更を加えます。 
    
5. 続行するように求められたら、[ **はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>エクスポート レポートの無効化に関してよく寄せられる質問

 **Results.csvレポートとManifest.xml レポートは何ですか?**
  
Results.csv ファイルとManifest.xml ファイルには、エクスポートされたコンテンツに関する追加情報が含まれています。
  
- **Results.csv** 検索結果としてダウンロードされる各項目に関する情報を含むExcelドキュメント。 電子メールの場合、結果ログには、次のような各メッセージに関する情報が含まれます。 
    
  - 移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。
    
  - メッセージが送信または受信された日付。
    
  - メッセージの件名行。
    
  - メッセージの送信者と受信者。
    
  - 検索結果をエクスポートするときに重複除去を有効にした場合、メッセージが重複メッセージであるかどうか。 重複するメッセージには、メッセージを重複として識別する値が **親 ItemId** 列に含まれます。 **親 ItemId** 列の値は、エクスポートされたメッセージの **Item DocumentId** 列の値と同じです。 
    
    SharePointサイトおよびOneDrive for Business サイトのドキュメントの場合、結果ログには、次のような各ドキュメントに関する情報が含まれます。
    
  - ドキュメントの URL。
    
  - ドキュメントがあるサイト コレクションの URL。
    
  - ドキュメントが最後に変更された日付。
    
  - ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。
    
- **Manifest.xml** 検索結果に含まれる各項目に関する情報を含むマニフェスト ファイル (XML 形式)。 このレポートの情報は、Results.csv レポートと同じですが、電子探索参照モデル (EDRM) で指定された形式です。 EDRM の詳細については、次を [https://www.edrm.net](https://www.edrm.net)参照してください。
    
 **これらのレポートのエクスポートをいつ無効にする必要がありますか?**
  
特定のニーズによって異なります。 多くの組織では、検索結果に関する追加情報を必要とせず、これらのレポートは必要ありません。
  
 **これを行う必要があるコンピューターは何ですか?**
  
 電子情報開示エクスポート ツールを実行するローカル コンピューターでレジストリ設定を変更する必要があります。 
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか?**
  
いいえ。コンピューターを再起動する必要はありません。 ただし、電子情報開示エクスポート ツールが実行されている場合は、レジストリ設定を変更した後、それを閉じてから再起動する必要があります。
  
 **既存のレジストリ キーは編集されるか、新しいキーが作成されますか?**
  
このトピックの手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリ キーが作成されます。 その後、.reg 編集ファイルを変更して再実行するたびに設定が編集されます。
