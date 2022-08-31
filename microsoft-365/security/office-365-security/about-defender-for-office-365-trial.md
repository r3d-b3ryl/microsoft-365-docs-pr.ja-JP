---
title: Microsoft Defender for Office 365試用版について
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdo
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Microsoft Defender for Office 365の試用版モードについて学習できます
ms.openlocfilehash: 883e91227ccf99835d85ea5253f89d765c3693df
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481374"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365試用版について

> [!IMPORTANT]
> 使いやすい[試用版プレイブックをMicrosoft Defender for Office 365](trial-playbook-defender-for-office-365.md)ですぐに使い始めましょう。 このプレイブックは、Microsoft Defender for Office 365を使用して組織を保護する方法を示すことで、無料試用版を最大限に活用するのに役立ちます。

Microsoft Defender for Office 365は、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによって発生する悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- **脅威保護ポリシー**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。
- **レポート**: 組織における Defender for Office 365 のパフォーマンスを監視するリアルタイム レポートを表示します。
- **脅威の調査および反応機能**: 最先端のツールを使用して、脅威を調査、把握、シミュレーション、および回避を行います。
- **自動調査および対応機能**: 脅威の調査と軽減にかかる時間と労力を節約します。

Microsoft Defender for Office 365試用版は、数回クリックするだけでDefender for Office 365プラン 2 の機能を無料で試す簡単な方法です。 これらの高度な機能については、次の表で説明します。

|機能|説明|
|---|---|
|[フィッシング対策ポリシーの排他的設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)|ユーザー偽装保護、ドメイン偽装保護、メールボックス インテリジェンス、高度なフィッシングのしきい値を取得します。|
|[添付ファイル保護](safe-attachments.md)|制御された爆発環境内の電子メールの添付ファイルやその他のファイルを調べて、新しいマルウェアや回避するマルウェアをキャッチします。|
|[リンク保護](safe-links.md)|クリック時間チェックを実行して、初期検査に合格した可能性のある URL が武器化されていないことを確認します。|
|[脅威トラッカー](threat-trackers.md)<sup>\*</sup>|有益なウィジェットとビューを使用して、組織に影響を与える可能性のあるサイバーセキュリティの問題を特定します。|
|[脅威エクスプローラー](threat-explorer.md)<sup>\*</sup>|Office 365メール内の脅威に関するほぼリアルタイムの情報を使用してハントします。|
|[自動調査と対応 (AIR)](office-365-air.md)<sup>\*</sup>|アラートがトリガーされると、脅威オブジェクトを自動的に見つけて修復します。|
|[攻撃シミュレーション トレーニング](attack-simulation-training.md)<sup>\*</sup>|フィッシング攻撃を特定し、適切に対応するようにユーザーをトレーニングします。|
|[キャンペーン ビュー](campaigns.md)<sup>\*</sup>|大規模な悪意のある電子メール アクティビティを調査して対応します。|
|[Defender for Office 365機能を使用したレポート](view-reports-for-mdo.md)|脅威保護の状態、URL の脅威の保護、メールの待機時間などのレポートを表示します。|
|[優先度アカウント保護](/microsoft-365/admin/setup/priority-accounts)<sup>\*</sup>|優先度アカウントとして識別したユーザーは、アラート、レポート、および調査でタグ付けされ、目立つように表示されます。フィルターで優先度タグを使用することもできます。|

<sup>\*</sup>この機能は、プラン 2 Defender for Office 365専用です。

## <a name="set-up-a-defender-for-office-365-trial"></a>Defender for Office 365試用版を設定する

試用版を使用すると、組織はDefender for Office 365機能を簡単に設定および構成できます。 セットアップ中に、事前[設定されたセキュリティ](preset-security-policies.md) ポリシーの Standard テンプレートを使用して、Defender for Office 365専用のポリシー (具体的には、[メール メッセージの安全な添付ファイル](safe-attachments.md)、[電子メール メッセージと Microsoft Teams の安全なリンク](safe-links.md)、および[フィッシング対策ポリシーでの偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) が適用されます。

既定では、これらのポリシーは組織内のすべてのユーザーに適用されますが、試用版のセットアップ中または設定後に、ポリシーの割り当てを特定のユーザーに変更できます。

> [!NOTE]
> 既存のスパム対策ポリシーは、スパム対策ポリシーの信頼性の高いスパム判定のために、アクション **メッセージを迷惑メールEmailフォルダーに移動** して構成されている可能性があります。 事前設定されたセキュリティ ポリシーの標準テンプレートでは、信頼性の高いスパムに対して検疫 **メッセージ** というアクションが使用され、事前設定されたセキュリティ ポリシーは常にカスタムスパム対策ポリシーまたは既定のスパム対策ポリシーの前に適用されます。 既定、標準、および厳格な設定の詳細については、「[EOP と Microsoft Defender for Office 365 セキュリティの推奨設定](recommended-settings-for-eop-and-office365.md)」を参照してください。

その他のワークロードも保護に使用できます (たとえば、[SharePoint の安全な添付ファイル、OneDrive、Microsoft Teams、](mdo-for-spo-odb-and-teams.md)[サポートされている Office アプリの安全なリンク](safe-links.md#safe-links-settings-for-office-apps)など)。

試用版のセットアップ中に、プラン 2 Defender for Office 365専用の応答機能 (たとえば、[AIR](office-365-air.md) と[脅威エクスプローラー](threat-explorer.md)も組織全体に対して設定されます。 ポリシースコープは必要ありません。

## <a name="licensing"></a>ライセンス

試用版のセットアップの一環として、Defender for Office 365 ライセンスが組織に自動的に適用されます。 最初の 90 日間、ライセンスは無料です。

試用版のライセンス カードには、次の情報が表示されます。

:::image type="content" source="../../media/mdo-trial-licensing-card.png" alt-text="Microsoft Defender for Office 365試用版のライセンス カード" lightbox="../../media/mdo-trial-licensing-card.png":::

- **[使用法の種類]** セクション:
  - **試用版**: 使用できる試用版Defender for Office 365ライセンスの数。

    > [!NOTE]
    > 他の場所では、使用可能な試用版ライセンスの数に対して 300 という値が表示される場合があります。 この値は正しくありません (組織に 300 人のユーザーが存在する場合を除く)。 利用可能な試用版ライセンスの数は、任意の値 300 ではなく、組織のサイズに対応します。

  - **支払済** み: 有料Defender for Office 365 ライセンスの数 (存在する場合)。

- **[使用法]** セクション: Defender for Office 365 ポリシーでカバーされているユーザーの数。
  - **検出&応答のみ**: 次のシナリオに含まれるユーザーの合計数。
    - 試用版の間、ポリシーの範囲を特定のユーザーに限定しました。
    - 特定のユーザーにスコープを設定するカスタム ポリシーがあります。
  - **完全な保護**: Defender for Office 365プラン 2 の機能 (AIR、脅威エクスプローラー、攻撃シミュレーション トレーニングなど) によって保護されているユーザーの合計数。

価格については、「[Microsoft Defender for Office 365](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-defender-office-365)」を参照してください。

## <a name="permissions"></a>アクセス許可

試用版を開始または終了するには、Azure Active Directory の **グローバル管理者** ロールまたは **セキュリティ管理者** ロールのメンバーである必要があります。 詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="additional-information"></a>その他の情報

試用版の使用を開始してから、変更や更新プログラムが利用できるようになるまで、最大で 2 時間かかる場合があります。 また、管理者はログアウトしてログインし直して変更を確認する必要があります。

## <a name="availability"></a>Availability

Defender for Office 365試用版は、特定の条件を満たし、既存のDefender for Office 365プラン 2 ライセンス (サブスクリプションまたはアドオンに含まれる) を持たない既存の顧客に段階的に展開されます。

## <a name="terms-and-conditions"></a>使用条件

詳細については、「[Microsoft Defender for Office 365試用版の使用条件&条件](defender-for-office-365-trial-terms-and-conditions.md)」を参照してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="q-how-do-i-extend-the-trial"></a>Q: 試用版を延長操作方法?

A: [試用版の延長に関するをご覧ください](/microsoft-365/commerce/try-or-buy-microsoft-365#extend-your-trial)。

### <a name="q-what-happens-to-my-data-after-the-trial-expires"></a>Q: 試用版の有効期限が切れた後、データはどうなりますか?

A: 試用版の有効期限が切れると、30 日間、試用版データ (以前に持っていなかったDefender for Office 365の機能のデータ) にアクセスできるようになります。 この 30 日間を過ぎると、Defender for Office 365試用版に関連付けられたすべてのポリシーとデータが削除されます。

### <a name="q-how-many-times-can-i-use-the-defender-for-office-365-trial-in-my-organization"></a>Q: 組織でDefender for Office 365試用版を何回使用できますか?

A: 最大 2 回。 最初の試用版の有効期限が切れた場合は、有効期限が切れた後、少なくとも 30 日間待ってから、Defender for Office 365試用版に再度登録する必要があります。 2 回目の試用版の後は、別の試用版に登録できません。

## <a name="learn-more-about-defender-for-office-365"></a>Defender for Office 365の詳細を確認する

Defender for Office 365は、組織が包括的な機能を提供することで、企業をセキュリティで保護するのに役立ちます。

Defender for Office 365の詳細については、この[対話型ガイド](https://aka.ms/MS365D.InteractiveGuide)を参照してください。

:::image type="content" source="../../media/microsoft-defender-for-office-365.png" alt-text="Microsoft Defender for Office 365概念図" lightbox="../../media/microsoft-defender-for-office-365.png":::

### <a name="prevention"></a>防止

堅牢なフィルター スタックにより、ビジネス メール侵害、資格情報フィッシング、ランサムウェア、高度なマルウェアなど、さまざまなボリュームベースの攻撃やターゲット攻撃を防ぎます。

- [フィッシング対策ポリシー: Defender for Office 365の排他的設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [添付ファイル保護](safe-attachments.md)
- [リンク保護](safe-links.md)

### <a name="detection"></a>検出

業界をリードする AI は、悪意のある疑わしいコンテンツを検出し、攻撃パターンを関連付けて、保護を回避するように設計されたキャンペーンを特定します。

- [Microsoft Defender for Office 365 のキャンペーン ビュー](campaigns.md)

### <a name="investigation-and-hunting"></a>調査と捜索

強力なエクスペリエンスは、Office 365全体の攻撃を追跡するための高度なハンティング機能を備えた、脅威の特定、優先順位付け、および調査に役立ちます。

- [脅威エクスプローラーとリアルタイム検出](threat-explorer.md)
- [Defender for Office 365のリアルタイム レポート](view-reports-for-mdo.md)
- [脅威トラッカー - 新機能とNoteworthy 機能 ](threat-trackers.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md) との統合

### <a name="response-and-remediation"></a>応答と修復

広範なインシデント対応と自動化機能により、セキュリティ チームの有効性と効率が向上します。

- [Microsoft Defender for Office 365の自動調査と対応 (AIR)](office-365-air.md)

### <a name="awareness-and-training"></a>認識とトレーニング

豊富なシミュレーション機能とトレーニング機能、およびクライアント アプリケーション内の統合されたエクスペリエンスにより、ユーザー認識が構築されます。

- [攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

### <a name="security-posture"></a>セキュリティ体制

推奨されるテンプレートと構成の分析情報は、お客様のセキュリティを確保し、維持するのに役立ちます。

- [EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)
- [EOP およびMicrosoft Defender for Office 365の保護ポリシー用の構成アナライザー](configuration-analyzer-for-security-policies.md)。

## <a name="give-feedback"></a>フィードバックを送信

お客様のフィードバックは、高度な攻撃から環境を保護するのに役立ちます。 製品の機能と試用版の結果に関するエクスペリエンスと印象を共有します。
