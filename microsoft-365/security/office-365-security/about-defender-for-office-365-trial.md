---
title: Microsoft Defender for Office 365試用版
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: 管理者は、管理者向け Microsoft Defender の試用版モードについてOffice 365
ms.openlocfilehash: 0164d7f5017ebf3b2076bf7231da4ca30a36427500c6782602e6e50812f914df
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817008"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365試用版

Microsoft Defender for Office 365、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによって組織が悪意のある脅威から保護します。 Defender for Office 365 には次のものが含まれます。

- **脅威保護ポリシー**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。
- **レポート**: リアルタイム レポートを表示して、組織内のパフォーマンスOffice 365 Defender を監視します。
- **脅威の調査および反応機能**: 最先端のツールを使用して、脅威を調査、把握、シミュレーション、および回避を行います。
- **自動調査および対応機能**: 脅威の調査と軽減にかかる時間と労力を節約します。

Microsoft Defender for Office 365 試用版は、Office 365 用の Defender の機能を試す最も簡単な方法であり、セットアップには 2 回のクリックが必要です。 試用版のセットアップが完了すると、Office 365プラン 1 とプラン 2 のすべての Defender 機能が組織内で最大 90 日間利用できます。 これらの高レベル機能については、次の一覧で説明します。

<br>

****

|機能|説明|
|---|---|
|[フィッシング対策ポリシーの排他的設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)|ユーザー偽装保護、ドメイン偽装保護、メールボックス インテリジェンス、高度なフィッシングしきい値を取得します。|
|[安全な添付ファイル](safe-attachments.md)|制御されたデトレーション環境で電子メールの添付ファイルや他のファイルを検査して、新しいマルウェアや回避的なマルウェアをキャッチします。|
|[リンク保護](safe-links.md)|クリック時のチェックを実行して、初期検査に合格した可能性がある URL が武器化されていないか確認します。|
|[脅威トラッカー](threat-trackers.md)<sup>\*</sup>|有益なウィジェットとビューを使用して、組織に影響を与える可能性のあるサイバーセキュリティの問題を特定します。|
|[脅威エクスプローラー](threat-explorer.md)<sup>\*</sup>|メール内の脅威に関するほぼリアルタイムの情報をOffice 365します。|
|[自動調査と対応 (AIR)](office-365-air.md)<sup>\*</sup>|アラートがトリガーされると、脅威オブジェクトを自動的に見つけて修復します。|
|[攻撃シミュレーションのトレーニング](attack-simulation-training.md)<sup>\*</sup>|フィッシング攻撃を識別し、適切に対応するためにユーザーをトレーニングします。|
|[キャンペーン ビュー](campaigns.md)<sup>\*</sup>|大規模な悪意のある電子メール アクティビティを調査して対応します。|
|[Defender を使用したレポートOffice 365機能](view-reports-for-mdo.md)|脅威保護の状態、URL の脅威保護、メールの待機時間などのレポートを表示します。|

<sup>\*</sup>Defender for Office 365試用版の一部として利用可能なプラン 2 の機能。

> [!NOTE]
> この記事で説明する自動構成は現在パブリック プレビューに含まれるので、組織では使用できない場合があります。

## <a name="terms-and-conditions"></a>使用条件

Defender for Office 365試用版は 90 日間利用可能で、すべてのユーザーに対して開始できます。 詳細については[、「Microsoft Defender for Office 365試用版&を参照してください](defender-for-office-365-trial-terms-and-conditions.md)。

## <a name="set-up-a-defender-for-office-365-trial"></a>試用版用に Defender をOffice 365する

試用版を使用すると、組織は簡単に Defender を設定し、その機能をOffice 365できます。 セットアップ中に、Office 365 の Defender 専用のポリシー (具体的には[、セーフ 添付](safe-attachments.md)ファイル[、セーフ リンク](safe-links.md)、スパム対策ポリシーの偽装[保護)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)は、事前設定されたセキュリティ ポリシー用の標準テンプレートを使用して[適用](preset-security-policies.md)されます。

既定では、これらのポリシーは組織内のすべてのユーザーを対象としますが、管理者はセットアップ中またはセットアップ後にポリシーをカスタマイズして、特定のユーザーにのみ適用できます。

セットアップ中に、Defender for Office 365応答機能 (Defender Office 365 P2 または同等の場合) も組織全体に対してセットアップされます。 ポリシースコープは必要ありません。

## <a name="licensing"></a>ライセンス

試用版のセットアップの一環として、ライセンスOffice 365 Defender が組織に自動的に適用されます。 ライセンスは、最初の 90 日間は無料です。

## <a name="permissions"></a>アクセス許可

試用版を開始または終了するには、グローバル管理者またはセキュリティ管理者の役割のメンバーである必要Azure Active Directory。 詳細については、「管理役割 [について」を参照してください](../../admin/add-users/about-admin-roles.md)。

## <a name="additional-information"></a>追加情報

試用版に登録した後、変更と更新プログラムが利用可能になるには、最大 2 時間かかる場合があります。 また、管理者はログアウトしてログインし、変更を確認する必要があります。

管理者は、管理者カードに移動して、任意の時点で試用版を <> できます。

## <a name="availability"></a>可用性

Office 365 の Defender 試用版は、特定の条件 (地域を含む) を満たす既存の顧客と、Office 365 プラン 1 またはプラン 2 ライセンス (サブスクリプションまたはアドオンに含まれる) の既存の Defender を持つユーザーに徐々に展開されています。

## <a name="learn-more-about-defender-for-office-365"></a>Defender for Office 365

Defender for Office 365機能の包括的なスレートを提供することで、組織が企業をセキュリティで保護するのに役立ちます。

Defender for Office 365については、この対話型ガイドを[参照してください](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)。

![Microsoft Defender for Office 365概念図](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>予防

堅牢なフィルター スタックにより、ビジネス メールの侵害、資格情報フィッシング、ランサムウェア、高度なマルウェアなど、さまざまなボリューム ベースの標的型攻撃を防止できます。

- [フィッシング対策ポリシー: Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [添付ファイル保護](safe-attachments.md)
- [リンク保護](safe-links.md)

### <a name="detection"></a>検出

業界をリードする AI は、悪意のあるコンテンツや疑わしいコンテンツを検出し、攻撃パターンを関連付け、保護を回避するために設計されたキャンペーンを特定します。

- [Microsoft Defender のキャンペーン ビュー (Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>調査と狩猟

強力なエクスペリエンスは、脅威の特定、優先順位付け、および調査に役立ち、高度な狩猟機能を使用して、攻撃を追跡Office 365。

- [脅威エクスプローラーとリアルタイム検出](threat-explorer.md)
- [Defender for Office 365](view-reports-for-mdo.md)
- [脅威トラッカー - 新機能とNoteworthy 機能 ](threat-trackers.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md) との統合

### <a name="response-and-remediation"></a>応答と修復

広範なインシデント対応と自動化機能により、セキュリティ チームの有効性と効率が向上します。

- [Microsoft Defender の自動調査と応答 (AIR) Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>認識とトレーニング

豊富なシミュレーションとトレーニング機能と、クライアント アプリケーション内の統合されたエクスペリエンスにより、ユーザーの認識が構築されます。

- [攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

### <a name="security-posture"></a>セキュリティの姿勢

推奨されるテンプレートと構成に関する分析情報は、お客様が安全にアクセスし、安全を確保するのに役立ちます。

- [EOP と Microsoft Defender でセキュリティ ポリシーを事前に設定Office 365](preset-security-policies.md)
- [EOP および Microsoft Defender の保護](configuration-analyzer-for-security-policies.md)ポリシー用の構成Office 365。

## <a name="give-feedback"></a>フィードバックを送信

フィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品機能と試用結果のエクスペリエンスとインプレッションを共有します。
