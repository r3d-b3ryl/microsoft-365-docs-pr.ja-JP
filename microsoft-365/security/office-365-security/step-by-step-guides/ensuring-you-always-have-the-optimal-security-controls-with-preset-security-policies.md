---
title: Microsoft Defender for Office 365の Standard または Strict の事前設定済みセキュリティ ポリシーをすばやく設定する手順
description: 製品で推奨されるセキュリティを確保するために、Microsoft Defender for Office 365で事前設定済みのセキュリティ ポリシーを設定する手順を実行します。 プリセット ポリシーは、 *Standard* または Strict のいずれかのセキュリティ プロファイルを設定 *します*。 これらを設定すると、これらのセキュリティ制御が管理および管理Microsoft Defender for Office 365されます。
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
ms.openlocfilehash: 095826d1633dddc55e055278d00148ce446a3719
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482342"
---
# <a name="set-up-steps-for-the-standard-or-strict-preset-security-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365で Standard または Strict の事前設定済みセキュリティ ポリシーの手順を設定する

Microsoft Defender for Office 365は、セキュリティ ポリシーを適用し、それを維持する方法を提供しましたか?

脅威の状況の変化に伴ってセキュリティ制御のベスト プラクティスが変更されたとき、または新しいコントロールが追加されると、*Microsoft は Standard* または *Strict* の事前設定されたセキュリティ ポリシーに割り当てられたユーザーのセキュリティ制御設定を *自動的に* 更新することをご存じですか?

事前設定されたセキュリティ ポリシー (*Standard* または *Strict*) を使用すると、ユーザーに対して Microsoft が *推奨するベスト プラクティスの構成* が常に提供されます。

**次の手順を使用して**、事前設定されたセキュリティ ポリシーを適用し、セキュリティ制御を管理および管理Microsoft Defender for Office 365 *します*。

## <a name="what-you-will-need"></a>必要なもの
- Microsoft Defender for Office 365 プラン 1 以降 (E5 に含まれる)
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分かかります。

## <a name="choose-between-standard-and-strict-policies"></a>Standard ポリシーと Strict ポリシーの間で選択する

厳格な事前設定済みのセキュリティ ポリシーには、より積極的な検出につながるセキュリティ制御のより積極的な制限と設定があり、ブロックされた電子メールがエンド ユーザーにリリースされる決定を管理者が伴います。

- より良いメールに不審なフラグが付けられることを意味する場合でも、より積極的な検出を必要とするユーザーの一覧を収集します。 通常、これらは、エグゼクティブ スタッフ、エグゼクティブ サポート スタッフ、および過去に高度にターゲットを絞ったユーザーです。

- エンド ユーザーがメールが適切であると考え、メッセージのリリースを要求する場合は、選択したユーザーがメールを確認してリリースするための管理者カバレッジを持っていることを確認します。

- 上記の条件が満たされている場合は、ユーザーを Strict プリセット セキュリティ ポリシーに配置する必要があります。 それ以外の場合は、ユーザーを Standard プリセット セキュリティ ポリシーに配置する必要があります。

> [!TIP]
> Standard と Strict のセキュリティ ポリシーの詳細については、この [記事](../../office-365-security/recommended-settings-for-eop-and-office365.md)を参照してください。

## <a name="enable-security-presets-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365でセキュリティ プリセットを有効にする

ユーザーの Standard セキュリティ プリセット ポリシーと Strict セキュリティ プリセット ポリシーの間で選択した後、各プリセットにユーザーを割り当てるには、さらにいくつかの手順が必要です。

1. Standard および Strict のセキュリティ プリセットに含めるユーザー、グループ、またはドメインを特定します。
1. Microsoft Security ポータル https://security.microsoft.comにログインします。.
1. 左側のナビゲーションにある **[Email & コラボレーション**] で、[**ポリシー&ルール**] を選択します。
1. **[脅威ポリシー**] を選択します。
1. [テンプレート ポリシー] 見出しの下にある **[事前設定されたセキュリティ** **ポリシー]** を選択する
1. Standard 保護プリセットの下にある [ **管理** ] を選択します。
1. [**すべての受信者]** を選択してテナント全体Exchange Online Protection適用するか、[**特定の受信者]** を選択して、保護ポリシーを適用するユーザー、グループ、またはドメインを手動で追加します。 [ **次へ** ] ボタンをクリックします。
1. [**すべての受信者]** を選択して Defender for Office 365 Protection テナント全体を適用するか、[**特定の受信者]** を選択して保護ポリシーを適用するユーザー、グループ、またはドメインを手動で追加します。 [ **次へ** ] ボタンをクリックします。
1. [ **偽装の保護** ] セクションで、偽装攻撃から保護するドメイン&電子メール アドレスを追加し、偽装保護を適用しない信頼された送信者とドメインを追加してから、[ **次へ**] を押します。
1. [ **確認** ] ボタンをクリックします。
1. Strict Protection プリセットで **[管理** ] リンクを選択します。
1. 手順 7 ~ 10 をもう一度繰り返しますが、ユーザーに対しては厳格な保護を適用する必要があります。 (該当する場合)
1. [ **確認** ] ボタンをクリックします。

> [!TIP]
> プリセット ポリシーの詳細については、こちらをクリック [してください](../../office-365-security/preset-security-policies.md)

## <a name="your-next-step-is-config-analyzer"></a>次の手順は Config Analyzer です

構成アナライザーを使用して、ユーザーが Microsoft のベスト プラクティスに従って構成されているかどうかを判断します。

> [!TIP]
> 構成アナライザーを使用すると、管理者は、設定が事前設定されたセキュリティ ポリシーの Standard または Strict 保護プロファイル設定の下にあるセキュリティ ポリシーを見つけて修正できます。 Configuration Analyzer の詳細については、 [こちらを参照してください](../../office-365-security/configuration-analyzer-for-security-policies.md)。

セキュリティで保護されたプリセットは、管理者が Microsoft のベスト プラクティスを実行 *していることを保証* するため、常にお勧めします。 ただし、カスタマイズされた構成が必要な場合もあります。 カスタム ポリシーについては [、こちらを参照してください](../../office-365-security/tenant-wide-setup-for-increased-security.md)。

