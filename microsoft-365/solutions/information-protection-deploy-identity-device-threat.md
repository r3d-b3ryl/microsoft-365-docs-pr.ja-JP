---
title: データプライバシー規制に ID、デバイス、脅威保護を使用する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365の ID、デバイス、脅威保護サービスによる個人データ侵害を防ぎます。
ms.openlocfilehash: a5aa97637b0d44b762d1a1146effdefb932ab47d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204973"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>データプライバシー規制に ID、デバイス、脅威保護を使用する

Microsoft 365には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために使用できるさまざまな ID、デバイス、脅威保護機能が用意されています。 この記事では、これらの分野でデータプライバシー規制に必要なものについて説明し、実装要件に対処するために役立つ詳細情報へのリンクを含む関連するMicrosoft 365機能とサービスの一覧を提供します。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>ID、デバイス、脅威の保護がデータ プライバシー規制とどのように関連しているか

データプライバシー規制は固有性が異なりますが、GDPR の記事 5(1)(f) に、次のように記載されています。

- 個人データは、個人データの適切なセキュリティを確保する方法で処理されます。これには、不正または違法な処理に対する保護、偶発的な損失、破壊、または損害に対する保護を含め、適切な技術的または組織的手段 ('整合性と機密性') を使用します。

個人データ侵害は、多くの場合、管理アカウントまたはエンド ユーザー アカウントの侵害と悪意のあるシステム アクセスによって引き起こされるためです。 たとえば、管理者アカウントのハッキングにより、顧客のクレジット カード番号やその他の個人情報が流出する可能性があります。 Microsoft 365で使用可能なすべての一般的に推奨される ID、デバイス、脅威の保護を実装する必要があります。これはコンプライアンス マネージャーのコンプライアンス スコアに反映されます。

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>評価作業とコンプライアンス マネージャーの結果を使用する

コンプライアンス マネージャーには、次のカテゴリを使用した ID、デバイス、脅威の保護が含まれます。

- ID が **コントロール アクセス** カテゴリに対応する
- デバイスが [デバイスの **管理** ] カテゴリに対応する
- 脅威の保護は、[ **脅威から保護** ] カテゴリに対応します。
 
これらが 4 つの主要なデータ プライバシー規制のサンプル セットで選択されている場合、コンプライアンス マネージャーは 90 個の改善アクションを指定します。そのほとんどには "27" というスコアが付きます。 このような多数は、これらのカテゴリのコンプライアンス マネージャーによって呼び出されるため、より一般的なものの一部が参照のためにここに一覧表示されます。

ID と **Control Access** カテゴリには [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) を使用します。これにより、次のことができます。

- リプレイ耐性認証を実装する ("中間者" 攻撃を防ぐため)
- レガシ認証をブロックする
- ユーザー リスクとユーザー サインイン リスク ポリシーを構成します。
- 管理者と管理者以外のユーザーに対して条件付きアクセスと多要素認証 (MFA) を有効にします。
- パスワード ポリシーを構成して適用します。
- Azure AD Privileged Identity Managementを使用して特権アカウントへのアクセスを制限します。
- 終了時にアクセスを無効にします。
- ユーザー アカウントと状態の変更を監査します。
- 役割グループと管理上の変更を確認します。

デバイスと [**デバイスの管理**] カテゴリの [Microsoft エンドポイント マネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)を使用すると、次のことができます。

- 脱獄されたモバイル デバイスとルート化されたモバイル デバイスをブロックします。
- モバイル デバイス管理のIntuneを構成します。
- Android、iOS、macOS、Windows デバイスのコンプライアンス ポリシーを作成します。
- Android、iOS、macOS、Windows デバイスのデバイス構成プロファイルを作成します。
- iOS とWindowsのアプリ保護ポリシーを作成します。
- ロック画面で情報を隠す。
- モバイル デバイスのパスワード ポリシーを実装します。
- 非アクティブ時にモバイル デバイスにロックを要求する。
- モバイル デバイスで複数のサインイン エラーをワイプする必要があります。

**[脅威から保護**] カテゴリの [Exchange Online ProtectionとMicrosoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md)を使用すると、次のことができます。

- 送信者認証 (SPF、DMARC、DKIM) を有効にします。
- フィッシング対策ポリシー Microsoft Defender for Office 365設定します。
- セーフ添付ファイルを実装します。
- セーフ リンクを実装します。
- マルウェアの検出と応答ポリシーを実装します。
- 送信スパム ポリシーと受信スパム ポリシーを実装します。

### <a name="references"></a>参照：

- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)
- [Office 365の脅威から保護する](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [添付ファイル保護](../security/office-365-security/safe-attachments.md)
- [リンク保護](../security/office-365-security/safe-links.md)
- [安全なドキュメント](../security/office-365-security/safe-docs.md)
