---
title: データプライバシー規制に id、デバイス、および脅威保護を使用する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Microsoft 365 の id、デバイス、および脅威保護サービスによる個人データ漏洩を防止します。
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520983"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>データプライバシー規制に id、デバイス、および脅威保護を使用する

Microsoft 365 には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために役立つ、id、デバイス、および脅威保護のさまざまな機能が用意されています。 この記事では、これらの分野で必要なデータプライバシーの規則について説明し、関連する Microsoft 365 の機能とサービスの一覧を提供し、実装要件に対応するための詳細情報へのリンクを提供します。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Id、デバイス、および脅威保護がデータプライバシー規制にどのように関連しているか

データのプライバシーに関する規定は、その特異性によって異なりますが、呼び出し対象の本質は GDPR の記事 5 (1) (f) に含まれています。これは次のように記述します。 

- 個人データの適切なセキュリティを確保する方法で処理されるのは、承認されていない、または違法な処理に対する保護や、適切な技術または組織上の手段 (「誠実で機密性」) を使用した、偶発的な損失、破壊または破損の防止です。

個人データ違反は、管理者またはエンドユーザーのアカウント侵害や悪意のあるシステムアクセスによって発生することがよくあります。 たとえば、管理者アカウントのハッキングによって、顧客のクレジットカード番号またはその他の個人情報を exfiltration することができます。 通常、Microsoft 365 で使用できるすべての推奨される id、デバイス、および脅威保護を実装する必要があります。これは、コンプライアンススコアに反映されます。

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>評価作業とコンプライアンススコアの結果の使用

コンプライアンススコアには、次のカテゴリを使用した id、デバイス、および脅威保護が含まれます。

- Id は、**コントロールアクセス**のカテゴリに対応します。
- デバイスの**管理**カテゴリに対応します。
- 脅威保護は**脅威からの保護**カテゴリに対応します。
 
これらの4つの主要なデータプライバシー規制のセット全体でこれらの規則が選択されている場合、コンプライアンススコアは90の改善アクションを指定します。ほとんどの場合、スコアは "27" です。 このような大規模な番号は、これらのカテゴリのコンプライアンススコアによって呼び出されているため、参考として、より一般的なもののいくつかを紹介します。

Id と**コントロールアクセス**カテゴリに[azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/)を使用します。これには、次の操作を実行できます。

- リプレイ対策認証を実装する ("Man-in-the-middle" 攻撃を防ぐため)
- レガシ認証をブロックする
- ユーザーのリスクとユーザーサインインリスクポリシーを構成します。
- 管理者および非管理者に対して、条件付きアクセスと多要素認証 (MFA) を有効にします。
- パスワードポリシーを構成して、適用します。
- Azure AD 特権 Id 管理を使用して、特権アカウントへのアクセスを制限します。
- 終了時にアクセスを無効にします。
- ユーザーアカウントと状態の変更を監査します。
- 役割グループと管理上の変更を確認します。

デバイス用の[Microsoft エンドポイントマネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)と**デバイスの管理**カテゴリを使用して、次のことを行うことができます。

- Jail が壊れていて、モバイルデバイスをブロックする。
- モバイルデバイス管理用に Intune を構成します。
- Android、iOS、macOS、Windows デバイスのコンプライアンスポリシーを作成します。
- Android、iOS、macOS、Windows デバイス用のデバイス構成プロファイルを作成します。
- IOS および Windows 用のアプリ保護ポリシーを作成します。
- ロック画面を使用して情報を隠す。
- モバイルデバイスのパスワードポリシーを実装します。
- モバイルデバイスが非アクティブ時にロックされるようにする。
- 複数のサインインエラーについてモバイルデバイスをワイプする必要があります。

[Exchange Online Protection と Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md)を使用して、[**脅威からの保護**] カテゴリを使用します。これには次のことができます。

- 送信者の認証を有効にします (SPF、DMARC、および DKIM)。
- Office 365 Advanced Threat Protection (ATP) フィッシング対策ポリシーをセットアップします。
- ATP の安全な添付ファイルを実装します。
- ATP の安全なリンクを実装します。
- マルウェアの検出と応答のポリシーを実装します。
- 送信および受信スパムポリシーを実装します。

### <a name="references"></a>設定

- [共通 ID とデバイスのアクセス ポリシー](../enterprise/identity-access-policies.md)
- [Office 365 で脅威から保護する](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [ATP の安全な添付ファイル機能](../security/office-365-security/atp-safe-attachments.md)
- [ATP の安全なリンク](../security/office-365-security/atp-safe-links.md)
- [ATP の安全なドキュメント](../security/office-365-security/safe-docs.md)
