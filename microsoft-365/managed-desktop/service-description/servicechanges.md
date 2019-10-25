---
title: サービスの変更と通信
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 00d1cb409364c017585c6afcd10a236ecbcdc3a0
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "37697901"
---
# <a name="service-changes-and-communication"></a>サービスの変更と通信

Microsoft では、Microsoft Managed Desktop の動作方法に関する詳細を変更する必要がある場合があります。 同様に、サービスに影響する変更を行う必要がある場合もあります。 このような変更は、重要な方法に応じて異なる方法で処理されます。 このトピックでは、主な変更点を定義し、その他の変更に対処する方法について説明します。



## <a name="changes-made-by-microsoft"></a>Microsoft によって加えられた変更

アクションを必要とするすべての主要な変更について、少なくとも30日前に通知が提供されます。 Microsoft Managed Desktop Admin portal メッセージングシステムを使用してお知らせします。

**主な変更点**は、これらの領域に影響を与える可能性があります。
- 毎日の生産性に影響を与える変更
- カスタマイズされた機能とアプリケーションに対する変更
- 表示可能な容量の拡大または縮小
- ヘルプデスクプロセスや参照資料または Url のユーザーの混乱や変更につながる可能性がある製品ブランド化の変更
- 日常の運用のためにサービスに必要なアクセス許可以外のアクセス許可を必要とする変更 (問題を防止または修正するアクションを除く)
- データの保存場所への変更
- サービスのスコープに新しいコンポーネントサービスまたはアプリケーションを追加する
- サービスの範囲からのコンポーネントサービスまたはアプリケーションの削除
- サービスに新しい機能を追加する

> [!NOTE]
> 30日通知ポリシーから除外されるインシデントまたはセキュリティの問題を軽減するために変更を加える必要がある場合があります。

ユーザーの利便性、セキュリティ、信頼性、およびレポートを向上させるために、定期的にサービスに変更を加えます。 これらの変更の例を次に示します。

- Windows および Office の更新プログラムのインストール
- デバイスに適用されるセキュリティベースラインの更新
- [Supported devices](device-list.md)

これらの変更は、確立されたチャネルを使用して通知します。 変更についての質問がある場合は、Microsoft Managed Desktop [Operations team](../working-with-managed-desktop/admin-support.md)にお問い合わせください。 サービスへの変更は、必要に応じて[変更履歴](../change-history-managed-desktop.md)にも記載されています。

Microsoft マネージドデスクトップの変更と通信は、次の2つの Microsoft ポリシーによって制御されます。
- [モダンライフサイクルポリシー](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 Change Communication Policy](https://docs.microsoft.com/office365/admin/manage/message-center?redirectSourcePath=%252fen-us%252farticle%252fMessage-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093&view=o365-worldwide)

## <a name="changes-you-make"></a>加えた変更

環境によっては、Microsoft マネージドデスクトップに影響を与える変更があります。 これらの主要な変更については、Microsoft Managed Desktop 管理ポータルでサービスリクエストを提出することによって、少なくとも30日の通知が送信されることを確認してください。 手順については、「 [Microsoft マネージドデスクトップの管理者サポート」を](../working-with-managed-desktop/admin-support.md)参照してください。 これにより、変更を計画および準備するのに十分な時間が確保され、中断を防ぐことができます。

主な変更点は、これらの領域に影響を与える可能性があります。

- Id システムおよびグループ
- ネットワークおよびネットワーク制御 (ファイアウォール、プロキシ、キャッシュ、VPN システムなど)
- クラウドサービスの構成にアクセスするためのコントロール
- ネットワークサービスの id またはセキュリティ保護に使用されるユーザーまたはデバイスの証明書
- サービスを操作する管理システム
- サービスを操作するセキュリティシステムまたはエージェント
- サービスに関連付けられている、またはで使用されているいずれかの Microsoft 365 クラウドサービスの構成

これらの変更は中断されない可能性があるため、事前に知らせる必要がありません。

- 孤立したオブジェクトのクリーンアップ
- サービスに対するユーザーの追加または削除
- Microsoft マネージドデスクトップの配信に重大な影響を与えないシステムの構成
- アプリケーションバージョンの更新 (VPN またはプロキシアプリケーションを除く)


