---
title: Microsoft Defender for Office 365 試用版について
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
description: 管理者は、Microsoft Defender for Office 365 の試用版モードについて学習できます。
ms.openlocfilehash: 6207ae117f06a0e5f10d4a7a47a251137c51df05
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233581"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365 試用版について

Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL)、コラボレーション ツールによって生じ得る悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- **脅威保護ポリシー**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。
- **レポート**: リアルタイム レポートを表示して、組織内の 365 Officeについて Defender を監視します。
- **脅威の調査および反応機能**: 最先端のツールを使用して、脅威を調査、把握、シミュレーション、および回避を行います。
- **自動調査および対応機能**: 脅威の調査と軽減にかかる時間と労力を節約します。

Office 365 試用版用の Microsoft Defender は、Office 365 の Defender の機能を試す最も簡単な方法であり、セットアップには 2 回のクリックのみ必要です。 試用版のセットアップが完了すると、Office 365 プラン 1 およびプラン 2 のすべての Defender 機能が組織で最大 90 日間利用可能になります。

> [!NOTE]
> この記事で説明する自動構成は、現在パブリック プレビュー中であり、お客様の場所では利用できない場合があります。

## <a name="terms-and-conditions"></a>使用条件

Defender for Office 365 試用版は 90 日間利用可能で、すべてのユーザーに対して開始できます。 詳しくは [、「365 試用版](defender-for-office-365-trial-terms-and-conditions.md)の使用条件Office Microsoft Defender に関するページ&覧ください。

## <a name="set-up-a-defender-for-office-365-trial"></a>Office 365 試用版用に Defender をセットアップする

試用版を使用すると、組織は 365 の機能に合Office Defender を簡単にセットアップして構成できます。 セットアップ中に、Office 365 の Defender 専用のポリシー (具体的には[](atp-safe-attachments.md)、安全な[](atp-safe-links.md)添付ファイル、安全なリンク、スパム対策ポリシーの偽装[保護)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)は、事前に設定されたセキュリティ ポリシーの標準テンプレートを使用して適用[されます。](preset-security-policies.md)

既定では、これらのポリシーの対象は組織内のすべてのユーザーですが、管理者はセットアップ中またはセットアップ後にポリシーをカスタマイズして、特定のユーザーにのみ適用できます。

セットアップ中に、MDO 応答機能 (MDO P2 または同等の機能) も組織全体に対して設定されます。 ポリシーのスコープは必要ありません。

## <a name="licensing"></a>ライセンス

試用版のセットアップの一環として、365 ライセンスOffice Defender が組織に自動的に適用されます。 ライセンスは最初の 90 日間無料です。

## <a name="permissions"></a>アクセス許可

試用版を開始または終了するには、Azure Active Directory のグローバル管理者ロールまたは **セキュリティ** 管理者ロールのメンバーである必要があります。 詳細については、「管理者ロール [について」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="additional-information"></a>追加情報

試用版に登録した後、変更と更新プログラムが利用可能になるのに最大 2 時間かかる場合があります。 また、管理者はログアウトしてログインし、変更を確認する必要があります。

管理者は、お試し版カードに移動して、いつでも <> できます。

## <a name="availability"></a>可用性

Office 365 向け Defender 試用版は、特定の条件 (地域を含む) を満たす既存のお客様や、既存の Defender for Office 365 プラン 1 またはプラン 2 のライセンス (サブスクリプションまたはアドオンに含まれる) を持たなかった既存のお客様に段階的に展開されています。

## <a name="learn-more-about-defender-for-office-365"></a>Defender for Office 365 の詳細

Defender for Office 365 は、包括的な機能を提供することで、組織が企業をセキュリティで保護するのに役立ちます。

Defender for Office 365 の詳細については、この対話型ガイド [を参照してください](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)。

![Microsoft Defender for Office 365 の概念図](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>防止

堅牢なフィルタリング スタックにより、ビジネス メールの侵害、資格情報のフィッシング、ランサムウェア、高度なマルウェアなど、さまざまなボリューム ベースの標的型攻撃を防止できます。

- [フィッシング対策ポリシー: Defender での Office 365 の排他的設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [添付ファイル保護](atp-safe-attachments.md)
- [リンク保護](atp-safe-links.md)

### <a name="detection"></a>検出

業界をリードする AI は、悪意のあるコンテンツや疑わしいコンテンツを検出し、攻撃パターンを関連付け、保護を回避するように設計されたキャンペーンを特定します。

- [Microsoft Defender for Office 365 のキャンペーン ビュー](campaigns.md)

### <a name="investigation-and-hunting"></a>調査と捜ティング

強力なエクスペリエンスは、脅威の特定、優先順位付け、調査に役立ち、高度な検索機能を使用して、Office 365 全体の攻撃を追跡できます。

- [脅威エクスプローラーとリアルタイムの検出](threat-explorer.md)
- [Defender での Office 365 のリアルタイム レポート](view-reports-for-atp.md)
- [脅威トラッカー - 新機能とNoteworthy 機能 ](threat-trackers.md)
- Microsoft [365 Defender との統合](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)

### <a name="response-and-remediation"></a>応答と修復

広範なインシデント対応と自動化機能により、セキュリティ チームの有効性と効率性が向上します。

- [Microsoft Defender での自動調査と対応 (AIR) for Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>認識とトレーニング

豊富なシミュレーション機能とトレーニング機能、およびクライアント アプリケーション内の統合エクスペリエンスにより、ユーザーの意識が向上します。

- [攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>セキュリティで保護された体勢

推奨されるテンプレートと構成に関する分析情報は、お客様のセキュリティを確保し、セキュリティを確保するのに役立ちます。

- [EOP と Microsoft Defender で Office 365 用のセキュリティ ポリシーを事前に設定する](preset-security-policies.md)
- [EOP および Microsoft Defender for Office 365](configuration-analyzer-for-security-policies.md)の保護ポリシーの構成アナライザー。

## <a name="give-feedback"></a>フィードバックを送信

お客様からのフィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品の機能と評価版の結果に関するエクスペリエンスとインプレッションを共有します。
