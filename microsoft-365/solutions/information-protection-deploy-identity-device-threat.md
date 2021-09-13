---
title: データプライバシー規制に ID、デバイス、および脅威保護を使用する
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
- m365solution-scenario
ms.custom: ''
description: ユーザーの ID、デバイス、および脅威保護サービスによる個人データ侵害をMicrosoft 365。
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59217863"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>データプライバシー規制に ID、デバイス、および脅威保護を使用する

Microsoft 365は、データプライバシーに関連するコンプライアンス規制の遵守に役立つ、組織が採用できる多数の ID、デバイス、および脅威保護機能を提供します。 この記事では、これらの分野で必要なデータプライバシー規制について説明し、実装要件に対処するための詳細へのリンクを含む関連する Microsoft 365 機能とサービスの一覧を提供します。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>ID、デバイス、および脅威保護がデータプライバシー規制とどのように関連付けるか

データプライバシーに関する規制は、その具体的な内容によって異なりますが、その本質は GDPR の第 5(1)(f) 条に示されています。

- 個人データは、不正または違法な処理に対する保護、偶発的な損失、破壊または損害に対する保護を含む、個人データの適切なセキュリティを確保する方法で、適切な技術的または組織的措置 ('整合性と機密性') を使用して処理されます。

個人データ侵害は、多くの場合、管理アカウントまたはエンド ユーザー アカウントの侵害と悪意のあるシステム アクセスによって引き起こされます。 たとえば、管理者アカウントのハッキングによって、顧客のクレジット カード番号や他の個人情報が浸透する可能性があります。 Microsoft 365 で使用可能なすべての一般的に推奨される ID、デバイス、および脅威保護を実装する必要があります。コンプライアンス スコアはコンプライアンス マネージャーに反映されます。

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>評価作業とコンプライアンス マネージャーの結果の使用

コンプライアンス マネージャーには、次のカテゴリを使用した ID、デバイス、および脅威の保護が含まれます。

- IDENTITY はコントロール アクセス **カテゴリに対応** します
- [デバイスの管理] カテゴリに **対応** するデバイス
- 脅威保護は、[脅威に対する **保護] カテゴリに対応** します。
 
これらが 4 つの主要なデータ プライバシー規制のサンプル セット全体で選択されている場合、コンプライアンス マネージャーは 90 の改善アクションを指定します。そのほとんどが "27" と評価されます。 このような大きな数は、これらのカテゴリのコンプライアンス マネージャーによって呼び出されるので、参照のために、より一般的な一部がここに一覧表示されます。

ID [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/)を使用して、次の操作を実行できます。

- 再生に強い認証を実装する ("Man in the middle" 攻撃を防ぐため)
- レガシ認証をブロックする
- ユーザー リスクとユーザー サインイン リスク ポリシーを構成します。
- 管理者および管理者以外のユーザーに対して条件付きアクセスと多要素認証 (MFA) を有効にします。
- パスワード ポリシーを構成して適用します。
- Azure アカウントを使用して特権アカウントへのアクセスをAD Privileged Identity Management。
- 終了時にアクセスを無効にします。
- ユーザー アカウントと状態の変更を監査します。
- 役割グループと管理上の変更を確認します。

デバイス[Microsoft エンドポイント マネージャー[](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)デバイスの管理] カテゴリで、次の機能を使用できます。

- 壊れた、根ざしたモバイル デバイスの脱獄をブロックします。
- モバイル デバイス管理用に Intune を構成します。
- Android、iOS、macOS、Windowsポリシーを作成します。
- Android、iOS、macOS、およびデバイスのデバイス構成プロファイルをWindowsします。
- iOS とアプリのアプリ保護ポリシーを作成Windows。
- ロック画面で情報を隠す。
- モバイル デバイスのパスワード ポリシーを実装します。
- 非アクティブ時にモバイル デバイスをロックする必要があります。
- 複数のサインインエラーでモバイル デバイスにワイプを要求する。

[[脅威Exchange Online Protection保護] カテゴリOffice 365](../security/office-365-security/defender-for-office-365.md) Microsoft Defender と **Microsoft** Defender を使用すると、次の機能を使用できます。

- 送信者認証 (SPF、DMARC、DKIM) を有効にします。
- フィッシング対策ポリシー Office 365 Microsoft Defender をセットアップします。
- 添付ファイルセーフ実装します。
- [リンクセーフ実装します。
- マルウェア検出ポリシーと応答ポリシーを実装します。
- 送信スパム ポリシーと受信スパム ポリシーを実装します。

### <a name="references"></a>参照:

- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)
- [脅威から保護Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [添付ファイル保護](../security/office-365-security/safe-attachments.md)
- [リンク保護](../security/office-365-security/safe-links.md)
- [安全なドキュメント](../security/office-365-security/safe-docs.md)
