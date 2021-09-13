---
title: 検索を作成する
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
description: ケース内の検索の保管担当者と保管場所を作成、定義、および選択するAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3050e176f495bd2fc23ac6237f1dac28b04088ec
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213924"
---
# <a name="create-a-search"></a>検索を作成する

ケースの **[検索]** タブで、[新しい検索] をクリックし、ウィザードに従って **新しい検索** を作成できます。

![ケース内の検索ウィザードAdvanced eDiscoveryします。](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>検索に名前を付け、説明を付け

ケースを含む各検索には、一意の名前が必要です。 必要に応じて、検索の説明を入力できます。 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>検索する保管担当者と保管場所を選択する

ケースに追加した保管担当者を指定して、検索する保管担当者コンテンツの場所を選択します。 カストディアンを選択すると、カストディアンにマップされているすべてのデータ ソースに対して検索が実行されます。 また、各保管担当者の選択したデータ ソースに検索を絞り込むオプションも用意されています。 カストディアンを追加してデータ ソースを管理する方法の詳細については、「保管担当者と一緒に作業する [」を参照してください](managing-custodians.md)。

## <a name="choose-non-custodial-locations"></a>保管以外の場所を選択する

カストディアンに関連付けされていないデータ ソースを検索する場合があります。 この場合、検索する場所を指定するか、特定の Microsoft サービスのすべてのコンテンツの場所 (すべての Exchange メールボックスまたはすべての SharePoint サイトと OneDrive アカウントの検索など) を選択できます。

## <a name="define-the-search-query-and-conditions"></a>検索クエリと条件を定義する

あらかじめ構築された条件カードを使用するか、キーワード クエリ言語 (KQL) を使用して、キーワード クエリと検索の条件を定義できます。 詳細については、「検索クエリの [ビルド」を参照してください](building-search-queries.md)。
