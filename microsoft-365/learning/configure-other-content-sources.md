---
title: 他のコンテンツ プロバイダーを追加Microsoft Viva ラーニング
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/22/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 他のプロバイダーを学習コンテンツ ソースとして構成する方法について説明Microsoft Viva ラーニング。
ROBOTS: NOINDEX
ms.openlocfilehash: 1a638131b9bf8cca41f7ee8575e472885929d3c8
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588007"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>他のコンテンツ プロバイダーを追加Microsoft Viva ラーニング

>[!NOTE]
>この機能はプレビューではサポートされていません。

一連の学習コンテンツ プロバイダーと学習管理システムは、Viva ラーニング。 このセットは、より多くのプロバイダーがプログラムに参加したり、プログラムの状態を変更したりすると、いつでも変更される可能性があります。

サードパーティのコンテンツ ソースは既定では有効になっていません。 これらのソースを有効にするには、次の表に[](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)示す特定の手順に従って、Microsoft 365 管理センターに追加する必要があります。

|コンテンツ プロバイダー  |構成手順  |
|---------|---------|
|Cornerstone OnDemand |[コンテンツ ソースとして Cornerstone OnDemand を構成する](configure-cornerstone-content-source.md)         |
|Go1     |[コンテンツ ソースとして Go1 を構成する](configure-go1-content-source.md)         |
|サバ島    |[コンテンツ ソースとしてサバを構成する](configure-saba-content-source.md)         |
|Skillsoft     |[Skillsoft をコンテンツ ソースとして構成する](configure-skillsoft-content-source.md)         |
|SAP SuccessFactors   |[SAP SuccessFactors をコンテンツ ソースとして構成する](configure-successfactors-content-source.md)         |
|Udemy   |[コンテンツ ソースとして Udemy を構成する](configure-udemy-content-source.md)         |

## <a name="content-ingestion-errors"></a>コンテンツの取り込みエラー

コンテンツの取り込み中にMicrosoft 365 管理センターが発生した場合は、次の手順の表を参照してください。 これは網羅的なリストであり、将来より多くのエラー コードが含まれる可能性があります。

|コンテンツ プロバイダー |エラー コード |エラー コードの説明 |
|:----------------|:----------|:----------------------|
|すべてのプロバイダー |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |指定した認証資格情報が無効です。 正しい資格情報を入力してください。 詳細については、Microsoft カスタマー サポートにお問い合わせください。 |
|すべてのプロバイダー |USR_ERROR_ACCESS_DENIED |パートナーによるアクセスが拒否されました。 入力した資格情報が正しいか、コンテンツ プロバイダーのサポート チームに連絡してください。 |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |SuccessFactors SFTP サーバーにファイルが存在しないので、新しいコンテンツは取り込めなかった。 |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |SuccessFactors SFTP サーバーで、必要なパッケージとして取り込まれた新しいコンテンツが見つかりませんでした。 |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |指定した認証資格情報が無効です。 Cornerstone OnDemand ポータルのビバ ラーニングアプリから資格情報がコピーされている必要があります。 |

## <a name="third-party-content-consumption"></a>サード パーティ製コンテンツの使用

Microsoft 365 管理センター からコンテンツ ソースとしてサード パーティ製のコンテンツ プロバイダーを追加すると、プロバイダーのコンテンツがビバ ラーニング アプリに流れ、エンド ユーザーに表示されます。

ユーザーがビバ ラーニング でコースをプレイすると、コンテンツ プロバイダーの Web ページに移動し、プロバイダーのサインイン ページにログイン資格情報を入力する必要があります。 [ビバ のコンテンツを使用してコンテンツを使用する方法の詳細については、ラーニング。](https://support.microsoft.com/office/viva-learning-preview-01bfed12-c327-41e0-a68f-7fa527dcc98a)
