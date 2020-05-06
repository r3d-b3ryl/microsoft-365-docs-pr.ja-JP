---
title: Microsoft 以外の365データを証拠に読み込む
f1.keywords:
- NOCSH
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
description: Office 365 以外のコンテンツのインポート機能を使用して、Office 以外の365ドキュメントをデータ調査の証拠にアップロードする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 499b1074b9a1e2026804eab2ac958fe7392e98ea
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034415"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>Microsoft 以外の365データを証拠に読み込む

データ調査で分析する必要があるすべてのドキュメントが Microsoft 365 にあるわけではありません。 Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 に存在しないドキュメントをデータ調査で分析できるように、証拠としてアップロードすることができます。

## <a name="before-you-begin"></a>はじめに

この手順の説明に従って Microsoft 以外の365機能をアップロードするには、次の条件を持っている必要があります。

- Microsoft 365 または Office 365 E5 サブスクリプション。

- Microsoft 以外の365のコンテンツをアップロードする対象となるすべてのユーザーには、適切な E5 または E5 アドオンライセンスが必要です。

- 既存の電子情報開示ケース。

- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。 *Alias@domainname*は、ユーザーのエイリアスおよびドメインである必要があります。 すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーに含めることができるのは*alias@domainname*フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。

- 電子情報開示の管理者または電子情報開示管理者のいずれかであるアカウントで、Microsoft 以外の365のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている。

- AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>Microsoft 以外の365コンテンツをデータ調査にアップロードする

1. **データ調査**を開いて、Microsoft 以外の365データがアップロードされることを調査します。  [**エビデンス**] タブをクリックし、データを読み込む証拠セットを選択します。  証拠セットをまだ作成していない場合は、ここで作成できます。  最後に、[**証明の管理**] をクリックし、[データ] セクションで [アップロード] を**表示**します。

2. [**ファイルのアップロード**] ボタンをクリックして、Microsoft 以外の365データインポートウィザードを起動します。

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。  準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。

![Microsoft 以外の365データインポートの準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. [**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の Microsoft 以外の365データが配置されます。  正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。

> [!NOTE]
> AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. [**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。  ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。

![Microsoft 以外の365データインポート用のファイルをアップロードする](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![AzCopy を使用して Microsoft 以外の365データをインポートする](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後に、[セキュリティ & コンプライアンスに戻し、[**次へ: ファイルの処理**] ボタンをクリックします。  これにより、アップロードされたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。  処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルが証拠セットで利用できるようになります。  処理が完了したら、ウィザードを閉じることができます。

![Microsoft 以外の365インポートプロセスファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

