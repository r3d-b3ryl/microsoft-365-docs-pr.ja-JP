---
title: Microsoft Defender for Office 365 試用版
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
description: 管理者は、Microsoft Defender for microsoft Defender for Office 365
ms.openlocfilehash: 1a86a73dbdb8f2549fb5dc03ece56497c5ff0b1e
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599797"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365 試用版

Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによって生じ得る悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- **脅威保護ポリシー**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。
- **レポート**: リアルタイム レポートを表示して、組織内の 365 のパフォーマンスOffice Defender を監視します。
- **脅威の調査および反応機能**: 最先端のツールを使用して、脅威を調査、把握、シミュレーション、および回避を行います。
- **自動調査および対応機能**: 脅威の調査と軽減にかかる時間と労力を節約します。

Office 365 試用版用の Microsoft Defender は、Office 365 の Defender の機能を試す最も簡単な方法であり、セットアップには 2 回のクリックしかかからない。 試用版のセットアップが完了すると、Office 365 プラン 1 とプラン 2 のすべての Defender 機能が組織内で最大 90 日間利用できます。

> [!NOTE]
> この記事で説明されている自動構成は現在パブリック プレビューに含まれるので、現在の場所では使用できない場合があります。

## <a name="terms-and-conditions"></a>使用条件

Defender for Office 365 試用版は 90 日間利用可能で、すべてのユーザーに対して開始できます。 詳細については [、「Microsoft Defender for Office 365 試用版&を参照してください](defender-for-office-365-trial-terms-and-conditions.md)。

## <a name="set-up-a-defender-for-office-365-trial"></a>365 試用版用に Defender をOfficeする

試用版を使用すると、組織は 365 の機能に合Office設定および構成できます。 セットアップ中に、Office 365 の Defender 専用のポリシー (具体的には[](safe-attachments.md)、安全な[](safe-links.md)添付ファイル、セーフ リンク、スパム対策ポリシーでの偽装[保護)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)は、事前設定されたセキュリティ[](preset-security-policies.md)ポリシー用の標準テンプレートを使用して適用されます。

既定では、これらのポリシーは組織内のすべてのユーザーを対象としますが、管理者はセットアップ中またはセットアップ後にポリシーをカスタマイズして、特定のユーザーにのみ適用できます。

セットアップ中に、MDO 応答機能 (MDO P2 または同等の機能) も組織全体に対して設定されます。 ポリシースコープは必要ありません。

## <a name="licensing"></a>ライセンス

試用版のセットアップの一環として、365 ライセンスOffice Defender が組織に自動的に適用されます。 ライセンスは、最初の 90 日間は無料です。

## <a name="permissions"></a>アクセス許可

試用版を開始または終了するには、Azure Active Directory のグローバル管理者またはセキュリティ管理者の役割のメンバーである必要があります。 詳細については、「管理役割 [について」を参照してください](../../admin/add-users/about-admin-roles.md)。

## <a name="additional-information"></a>追加情報

試用版に登録した後、変更と更新プログラムが利用可能になるには、最大 2 時間かかる場合があります。 また、管理者はログアウトしてログインし、変更を確認する必要があります。

管理者は、管理者カードに移動して、任意の時点で試用版を <> できます。

## <a name="availability"></a>可用性

Office 365 の Defender 試用版は、特定の条件 (地域を含む) を満たし、Office 365 プラン 1 またはプラン 2 ライセンス (サブスクリプションまたはアドオンとして含まれる) の既存の Defender を持つ既存の顧客に徐々に展開されています。

## <a name="learn-more-about-defender-for-office-365"></a>Defender for Office 365 の詳細

Defender for Office 365 は、組織が包括的な機能を提供することで企業をセキュリティで保護するのに役立ちます。

Defender for Office 365 の詳細については、この対話型ガイド [を参照してください](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)。

![Microsoft Defender for Office 365 概念図](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>予防

堅牢なフィルター スタックにより、ビジネス メールの侵害、資格情報フィッシング、ランサムウェア、高度なマルウェアなど、さまざまなボリューム ベースの標的型攻撃を防止できます。

- [フィッシング対策ポリシー: 365 の Defender Office設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [添付ファイル保護](safe-attachments.md)
- [リンク保護](safe-links.md)

### <a name="detection"></a>検出

業界をリードする AI は、悪意のあるコンテンツや疑わしいコンテンツを検出し、攻撃パターンを関連付け、保護を回避するために設計されたキャンペーンを特定します。

- [Microsoft Defender for microsoft Defender for Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>調査と狩猟

強力なエクスペリエンスは、脅威の特定、優先順位付け、および調査に役立ち、高度な狩猟機能を使用して、365 全体の攻撃Officeできます。

- [脅威エクスプローラーとリアルタイム検出](threat-explorer.md)
- [Defender for Office 365 のリアルタイム レポート](view-reports-for-mdo.md)
- [脅威トラッカー - 新機能とNoteworthy 機能 ](threat-trackers.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md) との統合

### <a name="response-and-remediation"></a>応答と修復

広範なインシデント対応と自動化機能により、セキュリティ チームの有効性と効率が向上します。

- [Microsoft Defender の自動調査と応答 (AIR) Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>認識とトレーニング

豊富なシミュレーションとトレーニング機能と、クライアント アプリケーション内の統合されたエクスペリエンスにより、ユーザーの認識が構築されます。

- [攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>セキュリティで保護された姿勢

推奨されるテンプレートと構成に関する分析情報は、お客様が安全にアクセスし、安全を確保するのに役立ちます。

- [EOP および Microsoft Defender の 365 用に事前設定Officeポリシー](preset-security-policies.md)
- EOP および Microsoft Defender の保護ポリシー用の構成[アナライザー (Office 365)](configuration-analyzer-for-security-policies.md)

## <a name="give-feedback"></a>フィードバックを送信

フィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品機能と試用結果のエクスペリエンスとインプレッションを共有します。
