---
title: ユーザー エクスペリエンスのローカライズ
description: ユーザーのデバイスをローカライズする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445983"
---
# <a name="localize-the-user-experience"></a>ユーザー エクスペリエンスのローカライズ

Microsoft Managed Desktop デバイスのユーザーは、セットアップ プロセス ("すぐに使用できる") または後で、選択した言語を選択できます。

## <a name="during-setup-the-out-of-box-experience"></a>セットアップ中 ("アウト オブ ボックス エクスペリエンス")

セットアップの完了プロセス中に、ユーザーは選択した言語を選択できます。 この選択は、次の属性に影響します。

- Windows 10 言語の機能:
    - 表示言語
    - キーボード言語
    - 言語関連のオンデマンド機能

- Microsoft 365 Apps for Enterprise 言語機能:
    - 表示言語
    - 校正ツールとオーサリング ツール

> [!NOTE]
> ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。

## <a name="after-completing-setup"></a>セットアップが完了した後

ユーザーは、セットアップ プロセスが完了した後、いつでも Windows 10 および Microsoft 365 Apps for Enterprise の言語を選択できます。 具体的には次のとおりです。

- Windows 10 言語の機能:
    - 表示言語
    - キーボード言語

- Microsoft 365 Apps for Enterprise 言語機能:
    - 表示言語
    - 校正ツールとオーサリング ツール

ユーザーがインストール [](#supported-languages)できる Microsoft 365 Apps for Enterprise のサポート言語を使用するには、モダン **Workplace-Office-Language_Packs** グループにユーザーを追加します。 言語は Intune ポータル サイトで使用できます。


## <a name="supported-languages"></a>サポートされている言語

新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。 製造元のイメージに、サポートされている言語リストで提供されている言語以外の言語が含まれる場合は、サービスで引き続きサポートされます。

既存のデバイスを再利用する場合は、適切なイメージを取得するために Microsoft アカウント担当者と作業する必要がある場合があります。 詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。

Microsoft [Managed](../service-description/device-images.md#universal-image) Desktop によって提供されるユニバーサル イメージには、次の言語と Windows 10 用が含まれます。

- 英語 (米国、GB、AU、CA、IN)
- スペイン語 (スペイン、メキシコ)
- 日本語
- フランス語 (フランス、カナダ)
- ドイツ語
- ポルトガル語 (ブラジル)
- イタリア語
- Chinese Simplified
- オランダ語  
- スウェーデン語
- デンマーク語  
- フィンランド語 
- ロシア語 
- ノルウェー語 (ブークモール)
- 韓国語
- Chinese Traditional
- ポーランド語
- トルコ語
- アラビア語
- ヘブライ語
- ポルトガル語 (ポルトガル)
- チェコ語
- ハンガリー語
- タイ語
- インドネシア語
- ギリシャ語
- スロバキア語
- ベトナム語
- スロベニア語
- クロアチア語
- ルーマニア語
- リトアニア語
- ブルガリア語
- セルビア語 (ラテン文字)
- ラトビア語
- ウクライナ語
- エストニア語

Microsoft 365 Apps for Enterprise では、若干異なるリストがサポートされている場合があります。

ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>サポートと操作の言語

### <a name="user-support"></a>ユーザー サポート
Microsoft Managed Desktop は英語でのみサポートを提供します。 ユーザーがヘルプ アプリで別の言語を選択した場合、Microsoft Managed Desktop から直接サポートするのではなく、一般的な Microsoft サポート チャネルからサポートを受け取る必要があります。 詳細については [、「Getting help for users 」を参照してください](../working-with-managed-desktop/end-user-support.md)。

ユーザーが他の言語でサポートを必要とする場合は、Microsoft 以外のサポート ソースまたは独自の組織からサポートを提供する必要があります。

### <a name="admin-support-and-operations"></a>管理者のサポートと操作
Microsoft Managed Desktop は、英語でのみ管理者サポートを提供します。 これには、管理ポータルと Microsoft Managed Desktop Operations とのすべての通信が含まれます。 特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。


