---
title: ユーザーの学習管理システムを追加Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 11/01/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 学習管理システムを学習コンテンツ ソースとして構成する方法については、Microsoft Viva ラーニング。
ms.openlocfilehash: 84f2e0d50b36f7fe54d82db9fb5564dcbbcbe9fa
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677144"
---
# <a name="add-learning-management-systems-for-microsoft-viva-learning"></a>ユーザーの学習管理システムを追加Microsoft Viva ラーニング

一連の学習管理システムは、ビバグループを通じてラーニング。 このセットは、より多くのプロバイダーがプログラムに参加したり、プログラムの状態を変更したりすると、いつでも変更される可能性があります。

ラーニング管理システムは既定で有効になっていません。 これらのソースを有効にするには、次の表に[](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)示す特定の手順に従って、Microsoft 365 管理センターに追加する必要があります。

>[!NOTE]
>学習管理システムを接続するにはプレミアムライセンスが必要です。 [ライセンスについて詳しくは、次をご覧ください](https://www.microsoft.com/microsoft-viva/learning)。

>[!NOTE]
>管理者ポータルで有効にしたソースのコンテンツラーニング、ビバ ユーザーが表示するには、24 ~ 48 時間かかる場合があります。

## <a name="learning-management-systems"></a>ラーニング管理システム

|ラーニング管理システム  |構成手順  |
|---------|---------|
|Cornerstone OnDemand |[コンテンツ ソースとして Cornerstone OnDemand を構成する](configure-cornerstone-content-source.md)         |
|サバ島    |[コンテンツ ソースとしてサバを構成する](configure-saba-content-source.md)         |
|SAP SuccessFactors   |[SAP SuccessFactors をコンテンツ ソースとして構成する](configure-successfactors-content-source.md)         |

>[!NOTE]
>利用可能な学習管理システムは変更される可能性があります。 組織によっては、ここに示されているのとは異なる学習管理システムにアクセスできる場合があります。

## <a name="content-ingestion-errors"></a>コンテンツの取り込みエラー

コンテンツの取り込み中にMicrosoft 365 管理センターが発生した場合は、次の手順の表を参照してください。 これは網羅的なリストであり、将来より多くのエラー コードが含まれる可能性があります。

|ラーニング管理システム |エラー コード |エラー コードの説明 |
|:----------------|:----------|:----------------------|
|すべての LMS |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |指定した認証資格情報が無効です。 正しい資格情報を入力してください。 詳細については、Microsoft カスタマー サポートにお問い合わせください。 |
|すべての LMS |USR_ERROR_ACCESS_DENIED |パートナーによるアクセスが拒否されました。 入力した資格情報が正しいか、コンテンツ プロバイダーのサポート チームに連絡してください。 |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |SuccessFactors SFTP サーバーにファイルが存在しないので、新しいコンテンツは取り込めなかった。 |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |SuccessFactors SFTP サーバーで、必要なパッケージとして取り込まれた新しいコンテンツが見つかりませんでした。 |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |指定した認証資格情報が無効です。 Cornerstone OnDemand ポータルで資格情報がMicrosoft Viva ラーニングコピーされている必要があります。 |

## <a name="content-consumption-for-end-users"></a>エンド ユーザーのコンテンツの使用

Microsoft 365 管理センター からコンテンツ ソースとして学習管理システムを追加すると、LMS のコンテンツがビバ ラーニング アプリに流れ、エンド ユーザーに表示されます。

ユーザーがビバ ラーニング でコースをプレイすると、LMS Web ページに移動し、LMS サインイン ページにログイン資格情報を入力する必要があります。 [ビバ のコンテンツを使用してコンテンツを使用する方法の詳細については、ラーニング。](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)
