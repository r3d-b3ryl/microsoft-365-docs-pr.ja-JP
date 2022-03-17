---
title: ユーザー エクスペリエンスをローカライズ
description: ユーザーのデバイスをローカライズする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c429a072d6ceb2d5d1472533649e30d1fc1a0078
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525003"
---
# <a name="localize-the-user-experience"></a>ユーザー エクスペリエンスをローカライズ

Microsoft Managed Desktop デバイスのユーザーは、セットアップ プロセス中 ("すぐに使用できる")、または後で、選択した言語を選択できます。

## <a name="during-setup-the-out-of-box-experience"></a>セットアップ中 ("アウト オブ ボックス エクスペリエンス")

セットアップ中に、ユーザーは選択した言語を選択できます。 この選択は、次の属性に影響します。

| 属性 | 説明 |
| ------ | ------ |
| Windows 10機能 | <ul><li>表示言語</li><li>キーボード言語</li><li>言語関連のオンデマンド機能</li><ul> |
| Microsoft 365 Apps機能Enterpriseの詳細 | <ul><li>表示言語</li><li>校正ツールとオーサリング ツール</li></ul> |

> [!NOTE]
> ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。

## <a name="after-completing-setup"></a>セットアップが完了した後

ユーザーは、セットアップ プロセスが完了した後Windows 10、Microsoft 365 AppsのEnterprise言語を選択できます。 特に次のような場合です。

| 機能 | 説明 |
| ------ | ------ |
| Windows 10機能 | <ul><li>表示言語</li><li>キーボード言語</li><ul> |
| Microsoft 365 Apps機能Enterpriseの詳細 | <ul><li>表示言語</li><li>校正ツールとオーサリング ツール</li></ul> |

## <a name="install-more-languages"></a>その他の言語をインストールする

> [!NOTE]
> 2022 年 3 月 16 日現在、言語を Microsoft Office に追加できるモダン Workplace-Office-Language_Packs グループをMicrosoft Office。 新しいメソッド (以下を参照) への移行は、2022 年 4 月に完了します。 移行期間中に問題が発生した場合は、サポートにお問い合 [わせください](../working-with-managed-desktop/admin-support.md)。

既定では、Microsoft Office管理者が必要です。Microsoft Managed Desktop は、標準ユーザーが Office アプリから言語アクセサリ パックを直接インストールできる Office ポリシーを展開します。 詳細については、「管理者ではないユーザーに追加の言語のインストールを許可 [する」を参照してください](/deployoffice/overview-deploying-languages-microsoft-365-apps#allow-users-who-arent-admins-to-install-additional-languages)。

## <a name="supported-languages"></a>サポートされている言語

新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。 製造元のイメージに、サポートされている言語リストに含まれていない言語が含まれている場合、デバイスはサービスで引き続きサポートされます。

既存のデバイスを再利用する場合は、Microsoft アカウント担当者と作業して適切な画像を取得する必要があります。 詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。

Microsoft [Managed](../service-description/device-images.md#universal-image) Desktop によって提供されるユニバーサル イメージには、次の言語と次のWindows 10。

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

> [!NOTE]
> Microsoft 365 AppsのEnterprise、少し異なるリストをサポートしている場合があります。

ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>サポートと操作の言語

### <a name="admin-support-and-operations"></a>管理者のサポートと操作

Microsoft Managed Desktop は、英語でのみ管理者サポートを提供します。 このサポートには、管理ポータルと Microsoft Managed Desktop Operations とのすべての通信が含まれます。 特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。
