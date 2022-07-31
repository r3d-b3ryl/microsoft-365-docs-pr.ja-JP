---
title: 事前設定されたセキュリティ ポリシーを使用して常に最適なセキュリティ制御を実現
description: 事前設定されたセキュリティ ポリシーを使用して、常に最適なセキュリティ制御を確保するための手順。 プリセット ポリシーを使用すると、Standard または Strict のいずれかのセキュリティ プロファイルを選択できます。 Microsoft は、Microsoft Defender for Office 365全体にわたるセキュリティ制御を管理および管理します。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 534e548dbd0950b387e757bfb81ebb446f617086
ms.sourcegitcommit: 7ac54e1952383d5cd5f084c6a9d247eb747d4904
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2022
ms.locfileid: "66994385"
---
# <a name="ensuring-you-always-have-the-optimal-security-controls-with-preset-security-policies"></a>事前設定されたセキュリティ ポリシーを使用して常に最適なセキュリティ制御を実現

事前設定されたセキュリティ ポリシーを使用すると、Standard または Strict のいずれかのセキュリティ プロファイルを選択し、Microsoft がMicrosoft Defender for Office 365全体でセキュリティ制御を管理および管理できます。

新しいコントロールが追加されるか、セキュリティ制御のベスト プラクティス設定が進化する脅威の状況に応じて変更された場合、Microsoft は Standard または Strict の事前設定されたセキュリティ ポリシーに割り当てられたユーザーのセキュリティ制御設定を自動的に更新します。 セキュリティ プリセット ポリシーを使用すると、ユーザーに対して Microsoft が推奨するベスト プラクティスの構成が常に用意されます。

## <a name="what-you-will-need"></a>必要なもの
- Microsoft Defender for Office 365 プラン 1 以降 (E5 に含まれる)
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分かかります。

## <a name="choosing-between-standard-and-strict-policies"></a>Standard ポリシーと Strict ポリシーの選択

厳格な事前設定済みのセキュリティ ポリシーには、より積極的な検出につながるセキュリティ制御のより積極的な制限と設定があり、ブロックされた電子メールがエンド ユーザーにリリースされる決定を管理者が伴います。

- より良いメールに不審なフラグが付けられることを意味する場合でも、より積極的な検出を必要とするユーザーの一覧を収集します。 通常、これらは、エグゼクティブ スタッフ、エグゼクティブ サポート スタッフ、および過去に高度にターゲットを絞ったユーザーです。

- エンド ユーザーがメールが適切であると考え、メッセージのリリースを要求する場合は、選択したユーザーがメールを確認してリリースするための管理者カバレッジを持っていることを確認します。

- 上記の条件が満たされている場合は、ユーザーを Strict プリセット セキュリティ ポリシーに配置する必要があります。 それ以外の場合は、ユーザーを Standard プリセット セキュリティ ポリシーに配置する必要があります。

> [!TIP]
> Standard と Strict のセキュリティ ポリシーの詳細については、この [記事](../../office-365-security/recommended-settings-for-eop-and-office365.md)を参照してください。

## <a name="enable-security-presets"></a>セキュリティ プリセットを有効にする

ユーザーの Standard セキュリティ プリセット ポリシーと Strict セキュリティ プリセット ポリシーの間で選択した後、各プリセットにユーザーを割り当てるには、さらにいくつかの手順が必要です。

1. Standard および Strict のセキュリティ プリセットに含めるユーザー、グループ、またはドメインを特定します。
1. Microsoft Security ポータル https://security.microsoft.comにログインします。.
1. 左側のナビゲーションにある **[Email & コラボレーション**] で、[**ポリシー&ルール**] を選択します。
1. **[脅威ポリシー**] を選択します。
1. [テンプレート ポリシー] 見出しの下にある **[事前設定されたセキュリティ** **ポリシー]** を選択する
1. Standard 保護プリセットの下にある [ **管理** ] を選択します。
1. [**すべての受信者]** を選択してテナント全体Exchange Online Protection適用するか、[**特定の受信者]** を選択して、保護ポリシーを適用するユーザー、グループ、またはドメインを手動で追加します。 [ **次へ** ] ボタンをクリックします。
1. [**すべての受信者]** を選択して Defender for Office 365 Protection テナント全体を適用するか、[**特定の受信者]** を選択して保護ポリシーを適用するユーザー、グループ、またはドメインを手動で追加します。 [ **次へ** ] ボタンをクリックします。
1. [**偽装の保護**] セクションで、偽装攻撃から保護するドメイン&電子メール アドレスを追加し、偽装保護を適用しない信頼された送信者とドメインを追加してから、[**次へ**] を押します。
3. [ **確認** ] ボタンをクリックします。
4. Strict Protection プリセットで **[管理** ] リンクを選択します。
5. 手順 7 ~ 10 をもう一度繰り返しますが、ユーザーに対しては厳格な保護を適用する必要があります。 (該当する場合)
7. [ **確認** ] ボタンをクリックします。

> [!TIP]
> 事前設定された polcies の詳細については、 [こちらをクリックしてください](../../office-365-security/preset-security-policies.md)

## <a name="next-steps"></a>次の手順

構成アナライザーを使用して、ユーザーが Microsoft のベスト プラクティスに従って構成されているかどうかを判断します。

> [!TIP]
> 構成アナライザーを使用すると、管理者は、設定が事前設定されたセキュリティ ポリシーの Standard または Strict 保護プロファイル設定の下にあるセキュリティ ポリシーを見つけて修正できます。 Configuration Analyzer の詳細については、 [こちらを参照してください](../../office-365-security/configuration-analyzer-for-security-policies.md)。

セキュリティで保護されたプリセットは、Microsoft のベスト プラクティスを常に実践していることを保証するため、常にお勧めします。 ただし、カスタマイズされた構成が必要な場合もあります。 カスタム ポリシーについては [、こちらを参照してください](../../office-365-security/tenant-wide-setup-for-increased-security.md)。

