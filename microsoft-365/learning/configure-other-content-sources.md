---
title: 他のコンテンツ プロバイダーを追加Microsoft Viva ラーニング
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 他のコンテンツ プロバイダーを、他のコンテンツ プロバイダーを学習用のコンテンツ ソースとして構成するMicrosoft Viva ラーニング。
ms.openlocfilehash: 4f1a8810f6b8615baa7e8b3fcd8d945ca08cf1d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668266"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>他のコンテンツ プロバイダーを追加Microsoft Viva ラーニング

一連の学習コンテンツ プロバイダーは、Viva ラーニング を通じて利用できます。 このセットは、より多くのプロバイダーがプログラムに参加したり、プログラムの状態を変更したりすると、いつでも変更される可能性があります。

一部の学習ソースは既定で有効にされ、プレミアムの Viva ライセンスなしでラーニングされます。 これらの学習ソースには、次のものが含まれます。

- LinkedIn ラーニング 125 コースを選択する
- Microsoft Learn
- Microsoft 365トレーニング

サードパーティのコンテンツ ソースは既定では有効になっていません。 これらのソースを有効にするには、次の表に[](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)示す特定の手順に従って、Microsoft 365 管理センターに追加する必要があります。

>[!NOTE]
>外部コンテンツ ソースを接続するにはプレミアムライセンスが必要です。ただし、無料のコースで LinkedIn を選択ラーニングがあります。 [ライセンスについて詳しくは、次をご覧ください](https://www.microsoft.com/microsoft-viva/learning)。

>[!NOTE]
>管理者ポータルで有効にしたソースのコンテンツラーニング、ビバ ユーザーが表示するには、24 ~ 48 時間かかる場合があります。 また、管理ポータルでコンテンツを無効にした後、LinkedIn ラーニング、Microsoft Learn、および Microsoft 365 トレーニングをビバ ラーニング から非表示にするには、24 ~ 48 時間かかる場合があります。

|コンテンツ プロバイダー  |構成手順  |
|---------|---------|
|Go1     |[コンテンツ ソースとして Go1 を構成する](configure-go1-content-source.md)         |
|Skillsoft     |[Skillsoft をコンテンツ ソースとして構成する](configure-skillsoft-content-source.md)         |
|Udemy   |[コンテンツ ソースとして Udemy を構成する](configure-udemy-content-source.md)         |
|edX    |次の手順に従って、アプリに edX を追加Microsoft 365 管理センター。    |
|Coursera    |以下の手順に従って、コースラを追加Microsoft 365 管理センター。    |
|Pluralsight    |以下の手順に従って、複数のサイトに Pluralsight を追加Microsoft 365 管理センター。    |
|Infosec    |以下の手順に従って、アプリに Infosec をMicrosoft 365 管理センター。    |
|Josh Bersin Academy    |以下の手順に従って、Josh Bersin Academy を追加Microsoft 365 管理センター。    |

1. 自分のアカウントに[ログインMicrosoft 365 管理センター。](https://admin.microsoft.com)
2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ ラーニング] を選択し、パネルで選択したコンテンツ プロバイダーまたは学習管理システムを有効にします。
3. 詳細を入力します。
4. **[保存]** を選択します。

>[!NOTE]
>利用可能なコンテンツ プロバイダーは変更される場合があります。 組織によっては、ここに示されているよりも多くのコンテンツ プロバイダーにアクセスできる場合があります。

## <a name="content-ingestion-errors"></a>コンテンツの取り込みエラー

コンテンツの取り込み中にMicrosoft 365 管理センターが発生した場合は、次の手順の表を参照してください。 これは網羅的なリストであり、将来より多くのエラー コードが含まれる可能性があります。

|コンテンツ プロバイダー |エラー コード |エラー コードの説明 |
|:----------------|:----------|:----------------------|
|すべてのプロバイダー |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |指定した認証資格情報が無効です。 正しい資格情報を入力してください。 詳細については、Microsoft カスタマー サポートにお問い合わせください。 |
|すべてのプロバイダー |USR_ERROR_ACCESS_DENIED |パートナーによるアクセスが拒否されました。 入力した資格情報が正しいか、コンテンツ プロバイダーのサポート チームに連絡してください。 |

## <a name="content-consumption-for-end-users"></a>エンド ユーザーのコンテンツの使用

Microsoft 365 管理センター からコンテンツ ソースとしてコンテンツ プロバイダーを追加すると、プロバイダーのコンテンツがビバ ラーニング アプリに流れ、エンド ユーザーに表示されます。

ユーザーがビバ ラーニング でコースをプレイすると、コンテンツ プロバイダーの Web ページに移動し、プロバイダーのサインイン ページにログイン資格情報を入力する必要があります。 [ビバ のコンテンツを使用してコンテンツを使用する方法の詳細については、ラーニング。](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)
