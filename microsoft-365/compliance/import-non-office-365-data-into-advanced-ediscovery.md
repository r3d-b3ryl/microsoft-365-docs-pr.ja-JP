---
title: Advanced eDiscovery 分析用に Microsoft 365 以外のコンテンツをインポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Microsoft 365 に保存されていないコンテンツを Azure BLOB にインポートして AeD で分析する方法
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662902"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Advanced eDiscovery (クラシック) 分析用に Microsoft 365 以外のコンテンツをインポートする

Advanced eDiscovery を使用して分析する必要がある可能性のあるすべてのドキュメントが Microsoft 365 に保存されるとは異なる。 Advanced eDiscovery の Microsoft 365 以外のコンテンツ インポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に保存されていないドキュメントを、Azure ストレージ BLOB をリンクされたケースにアップロードし、Advanced eDiscovery で分析できます。 この手順では、Microsoft 365 以外のドキュメントを分析のために Advanced eDiscovery に取り込む方法を示します。
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
> [!NOTE]
> Microsoft 365 以外のコンテンツの Advanced eDiscovery データ ストレージ アドオン サブスクリプションを購入できます。 これは、Advanced eDiscovery で分析されるコンテンツに対して排他的に使用できます。 「ビジネス向け [Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) のアドオンを購入または編集する」の手順に従って、Advanced eDiscovery ストレージ アドオンを購入します。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>365 以外のコンテンツOfficeアップロードする要件

この手順で説明するように、Office 365 以外のアップロード機能を使用するには、以下が必要です。
  
- Advanced Compliance Officeまたは E5 サブスクリプションを使用する 365 E3 をサポートします。
    
- 365 以外のコンテンツOfficeアップロードされるすべての保管担当者は、Advanced Compliance アドオンまたは E5 ライセンスを持っている必要があります。
    
- 既存の電子情報開示ケース。
    
- アップロードするファイルはすべて、保管担当者ごとに 1 つのフォルダーが含まれ、フォルダーの名前が次の形式 *alias@domainname。* この  *alias@domainname*  は、365 エイリアスOfficeドメインを持つユーザーである必要があります。 ルート フォルダーには  *、alias@domainname*  フォルダーを収集できます。 ルート フォルダーには、ルートフォルダー alias@domainname、ルート フォルダーにルース ファイルが含まれている必要はありません。
    
- 電子情報開示マネージャーまたは電子情報開示管理者であるアカウント。
    
- [Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) は、365 以外のコンテンツ フォルダー構造にアクセスOfficeコンピューターにインストールされます。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Advanced eDiscovery Office 365 以外のコンテンツをアップロードする


1. 電子情報開示マネージャーまたは電子情報開示管理者として電子情報開示を開き、非電子情報開示 365 データOfficeアップロードするケースを開きます。 ケースを作成する必要がある場合は、「セキュリティ コンプライアンス センターで電子情報開示ケースを管理する [」を &amp; 参照してください](ediscovery-cases.md)。
    
2. [Advanced **eDiscovery に切り替える] をクリックします**。

3. メニュー **から [Review Sets]** を選択します。

4. 既存のレビュー セットを選択するか、[レビュー セットの **追加] を選択します**。

5. [レビュー **セットの管理] を選択します**。

6. In the Non-Office 365 data card, select **View Uploads**.

7. [ファイル **のアップロード] を** 選択して、ファイルのアップロード ウィザードを開始します。

8. 最初のタブは **1 です。手順を準備します**。 [次 **へ] を選択します。ファイルをアップロードします**。

9. On the **2.[ファイル** のアップロード] タブでは、まだダウンロードしていない場合AzCopy.exeをダウンロードし、ファイルの場所へのパスを指定するように求めるメッセージが表示されます。 たとえば、 `C:\Upload`  このコマンドを実行するコマンドが表示AzCopy.exe。 使用 `C:\Upload` すると、次の情報が表示されます。

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. コマンド プロンプト ウィンドウを開き、AzCopy.exeコマンドを実行してデータを Azure にインポートします。 すべてのデータが読み込まれたら、[次へ: ファイルの処理 **] を選択します**。

11. 次のタブは **3 です。データが** 関連付けられている保管担当者が表示され、インポートされるデータの進行状況も表示されるプロセス ファイル。
        
    Azcopy 構文の詳細については、「Windows での AzCopy によるデータの [転送」を参照してください](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    Advanced eDiscovery 処理の詳細については、「プロセス モジュールを実行し、Advanced eDiscovery でデータを読み込む [(クラシック)」を参照してください](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。 
    
    > [!IMPORTANT]
    > ユーザーごとに 1 つのルート フォルダーが必要です。また、フォルダー名は新しいフォルダー <b>形式alias@domainnameがあります</b>  。 
   
    > [!IMPORTANT]
    > コンテナーが Advanced eDiscovery で正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなりました。 追加のコンテンツを収集し、Advanced eDiscovery 分析のケースに追加する場合は、新しい非 Office **365 データ コンテナー** を作成し、この手順を繰り返す必要があります。 
  
    > [!NOTE]
    > フォルダーの名前付けの問題が原因でコンテナーが正常に処理されない場合に問題を修正した場合でも、この記事の手順を使用して新しいコンテナーを作成し、再接続してアップロードし直す必要があります。
