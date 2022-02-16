---
title: サービスの変更とコミュニケーション
description: サービスに対する変更が発生して通信される方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 59c5c2c10a344c8edec047b5f9290fa5d3d08d75
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825435"
---
# <a name="service-changes-and-communication"></a>サービスの変更とコミュニケーション

場合によっては、Microsoft Managed Desktop の動作方法に関する詳細を変更する必要がある場合があります。 同様に、サービスにも影響を与える変更を加える必要があります。 このような変更は、重要な内容に応じて異なる方法で処理されます。 この記事では、重要な変更と見なす変更を定義し、その変更と他の変更の処理方法について説明します。

## <a name="changes-made-by-microsoft"></a>Microsoft によって行われた変更

アクションが必要な大きな変更については、少なくとも 30 日前に通知します。 Microsoft Managed Desktop Admin ポータル メッセージング システムを使用してお知らせします。

**主な変更** 点は、次に示す領域に影響を与える可能性がある変更点です。

- 毎日の生産性に影響を与える変更。
- カスタマイズされた機能とアプリケーションへの変更。
- 表示される容量の増減。
- ヘルプデスク プロセスや参照資料または URL でユーザーの混乱や変更を引き起こす可能性がある製品ブランド化の変更。
- サービスが日常業務で必要とするアクセス許可を超えるアクセス許可を必要とする変更 (問題を防止または修正するアクションを除く)。
- データの保存場所を変更します。
- サービスのスコープに新しいコンポーネント サービスまたはアプリケーションを追加する。
- サービスのスコープからコンポーネント サービスまたはアプリケーションを削除する。
- サービスに新しい機能を追加する。

> [!NOTE]
> 30 日間の通知ポリシーから除外されるインシデントやセキュリティの問題を軽減するために、変更が必要になる場合があります。

ユーザー エクスペリエンス、セキュリティ、信頼性、レポートを向上させるために、サービスに対して他の変更を定期的に行います。 これらの変更の例を次に示します。

- 更新プログラムWindowsインストールOfficeインストールします。
- デバイスに適用されるセキュリティ 基準の更新。
- サポートされているデバイス。 推奨されるデバイスを表示するには、ビジネス デバイス サイトの [ショップ] サイトで Microsoft Managed Desktop [Windows Proフィルター](https://www.microsoft.com/windows/business/devices)します。

これらの変更については、確立されたチャネルを使用して伝達します。 変更について質問がある場合は、Microsoft Managed Desktop Operations チームにお [問い合わせください](../working-with-managed-desktop/admin-support.md)。 サービスへの変更は、必要に応じて変更履歴にも [記録されます](../change-history-managed-desktop.md)。

Microsoft Managed Desktop の変更と通信は、次の 2 つの Microsoft ポリシーによって管理されます。

- [最新のライフサイクル ポリシー](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365通信ポリシーの変更](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a>加えた変更

環境で行う変更の中には、Microsoft Managed Desktop に影響を与える可能性があります。

これらの大きな変更については、Microsoft Managed Desktop Admin ポータルでサポート要求を提出して、少なくとも 30 日間の通知をお願いします。 手順については、「 [Microsoft Managed Desktop の管理者サポート」を参照してください](../working-with-managed-desktop/admin-support.md)。 これにより、中断を回避するために、変更を計画して準備するための十分な時間を確保できます。

**主な変更** 点は、次に示す領域に影響を与える可能性がある変更点です。

- ID システムとグループ。
- ファイアウォール、プロキシまたはキャッシュ、VPN システムなどのネットワークおよびネットワークコントロール。
- クラウド サービス構成にアクセスするコントロール。
- ネットワーク サービスの ID またはセキュリティ保護に使用されるユーザー証明書またはデバイス証明書。
- サービスと対話する管理システム。
- サービスと対話するセキュリティ システムまたはエージェント。
- サービスに関連付けられたMicrosoft 365、またはサービスによって使用されるクラウド サービスの構成。

これらの変更は中断される可能性が高くないので、前もってそれらの変更についてお知らせする必要はありません。

- 孤立したオブジェクトのクリーンアップ。
- サービスへのユーザーの追加または削除。
- Microsoft Managed Desktop の配信に大きな影響を与えるシステムの構成。
- VPN またはプロキシ アプリケーションを除く、アプリケーションのバージョンの更新。
