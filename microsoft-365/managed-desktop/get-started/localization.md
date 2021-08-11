---
title: ユーザー エクスペリエンスをローカライズ
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
ms.openlocfilehash: a1a042047e3203d8c401f5435e87bafa20aa952ca9e32a051b47ea3a038b7aad
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800692"
---
# <a name="localize-the-user-experience"></a>ユーザー エクスペリエンスをローカライズ

デバイスのMicrosoft マネージド デスクトップは、セットアップ プロセス ("すぐに使用できる") または後で、選択した言語を選択できます。

## <a name="during-setup-the-out-of-box-experience"></a>セットアップ中 ("アウト オブ ボックス エクスペリエンス")

セットアップの完了プロセス中に、ユーザーは選択した言語を選択できます。 この選択は、次の属性に影響します。

- Windows 10機能:
    - 表示言語
    - キーボード言語
    - 言語関連のオンデマンド機能

- Microsoft 365 Apps機能Enterprise次の情報を参照してください。
    - 表示言語
    - 校正ツールとオーサリング ツール

> [!NOTE]
> ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。

## <a name="after-completing-setup"></a>セットアップが完了した後

ユーザーは、セットアップ プロセスが完了した後Windows 10、Microsoft 365 AppsのEnterprise言語を選択できます。 具体的には次のとおりです。

- Windows 10機能:
    - 表示言語
    - キーボード言語

- Microsoft 365 Apps機能Enterprise次の情報を参照してください。
    - 表示言語
    - 校正ツールとオーサリング ツール

ユーザーがインストール [できる](#supported-languages)Microsoft 365 Apps Microsoft 365 Apps Enterprise のサポートされている言語を使用するには、モダン **Workplace-Office-Language_Packs** グループにユーザーを追加します。 言語は、次のIntune ポータル サイト。


## <a name="supported-languages"></a>サポートされている言語

新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。 製造元のイメージに、サポートされている言語リストで提供されている言語以外の言語が含まれる場合は、サービスで引き続きサポートされます。

既存のデバイスを再利用する場合は、適切なイメージを取得するために Microsoft アカウント担当者と作業する必要がある場合があります。 詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。

ユーザー[が提供する](../service-description/device-images.md#universal-image)ユニバーサル Microsoft マネージド デスクトップには、次の言語と次のWindows 10。

- アラビア語
- ブルガリア語
- 中国語 (簡体字)
- 中国語 (繁体字)
- クロアチア語
- チェコ語
- デンマーク語  
- オランダ語  
- 英語 (米国、GB、AU、CA、IN)
- エストニア語
- フィンランド語 
- フランス語 (フランス、カナダ)
- ドイツ語
- ギリシャ語
- ヘブライ語
- ハンガリー語
- インドネシア語
- イタリア語
- 日本語
- 韓国語
- ラトビア語
- リトアニア語
- ノルウェー語 (ブークモール)
- ポーランド語
- ポルトガル語 (ブラジル)
- ポルトガル語 (ポルトガル)
- ルーマニア語
- ロシア語 
- セルビア語 (ラテン文字)
- スロバキア語
- スロベニア語
- スペイン語 (スペイン、メキシコ)
- スウェーデン語
- タイ語
- トルコ語
- ウクライナ語
- ベトナム語

Microsoft 365 AppsのEnterprise、少し異なるリストをサポートしている場合があります。

ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>サポートと操作の言語

### <a name="user-support"></a>ユーザー サポート
Microsoft マネージド デスクトップは英語でのみサポートされます。 ユーザーがアプリで別の言語を問い合わせ場合、ユーザーは一般的な Microsoft サポート チャネルから直接サポートするのではなく、サポートを受Microsoft マネージド デスクトップ。 詳細については [、「Getting help for users 」を参照してください](../working-with-managed-desktop/end-user-support.md)。

ユーザーが他の言語でサポートを必要とする場合は、Microsoft 以外のサポート ソースまたは独自の組織からサポートを提供する必要があります。

### <a name="admin-support-and-operations"></a>管理者のサポートと操作
Microsoft マネージド デスクトップは英語でのみ管理者サポートを提供します。 これには、管理ポータルと、管理操作との通信Microsoft マネージド デスクトップ含まれます。 特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。


