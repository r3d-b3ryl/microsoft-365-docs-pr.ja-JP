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
ms.openlocfilehash: daafcf003ded35868413d99c11ec1bf3941dca9f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634159"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Microsoft 以外の365コンテンツをインポートして高度な電子情報開示 (クラシック) 分析を行う

上級電子情報開示を使用して分析する必要があるすべてのドキュメントが Microsoft 365 に存在するわけではありません。 Advanced 電子情報開示の Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に存在しないドキュメントを、ケースにリンクされた Azure ストレージ blob にアップロードし、アドバンスト eDiscovery で分析することができます。 この手順では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法を示します。
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
> [!NOTE]
> Microsoft 以外の365コンテンツについては、高度な電子情報開示データ記憶域アドオンサブスクリプションを購入できます。 これは、Advanced eDiscovery で分析するコンテンツにのみ使用できます。 「 [Microsoft 365 for business のアドオンを購入または編集する](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)」の手順に従って、Advanced eDiscovery storage アドオンを購入します。 
  
## <a name="before-you-begin"></a>始める前に

この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。
  
- 高度なコンプライアンスアドオンまたは E5 サブスクリプションを使用した Office 365 E3
    
- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。
    
- 既存の電子情報開示ケース
    
- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。 *Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーには*alias@domainname*フォルダーのみ含めることができます。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。 
    
- 電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント
    
- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする


1. 電子情報開示マネージャーまたは電子情報開示管理者として、**電子情報開示**を開いて、Office 以外の365データがアップロードされるケースを開きます。 ケースを作成する必要がある場合は、「 [ &amp; Security コンプライアンスセンターで電子情報開示ケースを管理](ediscovery-cases.md)する」を参照してください。
    
2. [**高度な電子情報開示に切り替え] を**クリックします。
    
3. [**ソースの種類**] で **、[Office 以外の365データ**] を選択します。
    
4. [**コンテナーの追加**] をクリックします。 コンテナーの名前を指定し、説明を追加します。
    
5. [コンテナー] ボックスの一覧から新しく追加したコンテナーを選択し、[コンテナー詳細] ウィンドウに表示される URL をコピーして、ウィンドウを閉じます。
    
6. 管理者としてコマンドプロンプトを開き、AzCopy がインストールされているフォルダーにディレクトリを変更します。
    
7. AzCopy コマンドラインを作成して、次のようにファイルをアップロードします。
    
    AzCopy/Source: "*ローカルコンピューター上のルートフォルダーへの完全なパス*"/Dest: "*コンテナー URL があるかどうか*。  "/Destsas:"*コンテナー url の残りの部分を end* "/S. 
    
    たとえば、次のような値を使用します。 
    
  - ルートフォルダー-c/一度収集したデータ 
    
  - コンテナーの url https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; sr =&amp;c Si = NonOfficeData15%&amp;7C0 sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d
    
    AzCopy コマンドライン構文は次のようになります。
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Azcopy 構文の詳細については、「 [Windows での AzCopy を使用してデータを転送する](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)」を参照してください。 
    
    > [!IMPORTANT]
    > ユーザーごとに1つのルートフォルダーが必要で、フォルダー名は*alias@domainname*形式である必要があります。 
  
8. フォルダーのアップロードが完了したら、[Advanced eDiscovery] に切り替えます。 アップロードしたフォルダーの内容は、高度な電子情報開示で処理する準備ができました。 コンテナーを選択し、[プロセス] ボタンをクリックします。 高度な電子情報開示の処理の詳細については、「 [Process モジュールを実行する」および「Advanced ediscovery でデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。
    
    > [!IMPORTANT]
    > 上級電子情報開示でコンテナーが正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなります。 追加のコンテンツを収集し、高度な電子情報開示分析のケースに追加する場合は、 **Office 365 以外**の新しいデータコンテナーを作成し、この手順を繰り返す必要があります。 
  
    > [!NOTE]
    > *フォルダーの名前付けの問題によってコンテナーが正常に処理されず*に問題が修正された場合は、この記事の手順を使用して、新しいコンテナーと再接続を作成し、再度アップロードする必要があります。
