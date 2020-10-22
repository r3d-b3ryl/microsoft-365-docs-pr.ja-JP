---
title: Microsoft 以外の365コンテンツをインポートして高度な電子情報開示分析を行う
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: Microsoft 365 に保存されていないコンテンツを Azure blob にインポートして、AeD で分析できるようにする手順
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636954"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Microsoft 以外の365コンテンツをインポートして高度な電子情報開示 (クラシック) 分析を行う

上級電子情報開示を使用して分析する必要があるすべてのドキュメントが Microsoft 365 に存在するわけではありません。 Advanced 電子情報開示の Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に存在しないドキュメントを、ケースにリンクされた Azure ストレージ blob にアップロードし、アドバンスト eDiscovery で分析することができます。 この手順では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法を示します。
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
> [!NOTE]
> Microsoft 以外の365コンテンツについては、高度な電子情報開示データ記憶域アドオンサブスクリプションを購入できます。 これは、Advanced eDiscovery で分析するコンテンツにのみ使用できます。 「 [Microsoft 365 for business のアドオンを購入または編集する](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 」の手順に従って、Advanced eDiscovery storage アドオンを購入します。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Office 以外の365コンテンツをアップロードするための要件

この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。
  
- 高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。
    
- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。
    
- 既存の電子情報開示ケース。
    
- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式  *alias@domainname*  であるフォルダーにアップロードされます。 *Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての  *alias@domainname*  フォルダーをルートフォルダーに収集できます。 ルートフォルダーに含めることができるのは  *alias@domainname*  フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。
    
- 電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント。
    
- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする


1. 電子情報開示マネージャーまたは電子情報開示管理者として、 **電子情報開示**を開いて、Office 以外の365データがアップロードされるケースを開きます。 ケースを作成する必要がある場合は、「 [Security &amp; コンプライアンスセンターで電子情報開示ケースを管理](ediscovery-cases.md)する」を参照してください。
    
2. [ **高度な電子情報開示に切り替え] を**クリックします。

3. メニューから [ **レビューセット** ] を選択します。

4. 既存のレビューセットを選択するか、[ **レビューセットの追加**] を選択します。

5. [ **レビューセットの管理**] を選択します。

6. Office 365 以外のデータカードで、[ **アップロードの表示**] を選択します。

7. [ **ファイルのアップロード** ] を選択して、ファイルアップロードウィザードを開始します。

8. 最初のタブは **1 です。準備手順**。 [ **次へ: ファイルのアップロード**] を選択します。

9. **2[ファイルのアップロード**] タブまだインストールしていない場合は、AzCopy.exe ダウンロードするかどうかを確認するメッセージが表示されたら、ファイルの場所へのパスを指定します。 たとえば、に `C:\Upload`  は AzCopy.exe を実行するコマンドが表示されます。 を使用 `C:\Upload` すると、次のように表示されます。

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. コマンドプロンプトウィンドウを開き、AzCopy.exe コマンドを実行して、データを Azure にインポートします。 すべてのデータを読み込んだら、[ **次へ: ファイルの処理**] を選択します。

11. 次のタブは **3 です。** データが関連付けられている保管担当者が表示されるファイルを処理し、インポートされるデータの進行状況も表示します。
        
    Azcopy 構文の詳細については、「 [Windows での AzCopy を使用してデータを転送する](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)」を参照してください。 
    
    高度な電子情報開示処理の詳細については、「 [Process module を実行する」および「Advanced ediscovery (classic) でデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。 
    
    > [!IMPORTANT]
    > ユーザーごとに1つのルートフォルダーが必要で、フォルダー名は <b>alias@domainname</b>  形式である必要があります。 
   
    > [!IMPORTANT]
    > 上級電子情報開示でコンテナーが正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなります。 追加のコンテンツを収集し、高度な電子情報開示分析のケースに追加する場合は、 **Office 365 以外** の新しいデータコンテナーを作成し、この手順を繰り返す必要があります。 
  
    > [!NOTE]
    > *フォルダーの名前付けの問題によってコンテナーが正常に処理されず*に問題が修正された場合は、この記事の手順を使用して、新しいコンテナーと再接続を作成し、再度アップロードする必要があります。
