---
title: Office 以外の365データを証拠に読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e05dc26159545e4daf7a8f4109268a1657fd62d6
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "38686806"
---
# <a name="load-non-office-365-data-into-evidence"></a>Office 以外の365データを証拠に読み込む

データ調査で分析する必要があるすべてのドキュメントが Office 365 にあるわけではありません。 Office 365 以外のコンテンツインポート機能を使用すると、Office 365 に存在しないドキュメントを証拠にアップロードして、データの調査で分析することができます。

>[!Note]
>データの調査には、組織のための高度なコンプライアンスアドオンまたは E5 サブスクリプションと共に Office 365 E3 が必要です。 その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。

## <a name="before-you-begin"></a>始める前に

この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。

- 高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。

- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。

- 既存の電子情報開示ケース。

- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。 *Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーに含めることができるのは*alias@domainname*フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。

- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。

- AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a>Office 365 以外のコンテンツをデータ調査にアップロードする

1. Open * * * * データ調査 * *、Office 以外の365データがアップロードされることを調査します。  [**証拠**] タブをクリックし、Office 以外の365データを読み込む証拠セットを選択します。  証拠セットをまだ作成していない場合は、ここで作成できます。  最後に、[**証明の管理**] をクリックし、[Office 以外の365データ] セクションの [アップロードを**表示**する] をクリックします。

2. [**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。

![ファイルをアップロードする](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。  準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。

![Office 以外の365データインポートの準備](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. [**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。  正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。

> [!NOTE]
> AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. [**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。  ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。

![Office 以外の365データインポート用のファイルをアップロードする](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 データをインポートするために AzCopy を使用する](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後に、[セキュリティ & コンプライアンスに戻し、[**次へ: ファイルの処理**] ボタンをクリックします。  これにより、アップロードされたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。  処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルが証拠セットで利用できるようになります。  処理が完了したら、ウィザードを閉じることができます。

![Office 以外の365インポート処理ファイル](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

