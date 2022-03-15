---
title: 基準計画を使用した標準テナント構成の展開の概要
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseを使用して標準テナント構成を展開する方法について説明します。
ms.openlocfilehash: 643bb962277d30caf8ea067b9276a5986af8914f
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504505"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>基準計画を使用した標準テナント構成の展開の概要 

Microsoft 365 Lighthouseベースラインを使用すると、複数の顧客テナント間でセキュリティ設定Microsoft 365管理できる、反復可能で拡張性の高い方法が提供されます。 ベースラインは、テナントのユーザー、デバイス、およびデータをセキュリティで保護するコア セキュリティ ポリシーとコンプライアンス標準を展開する標準的なテナント構成を提供します。

既定の基準計画とその展開手順は、ライトハウス内から表示できます。 基準計画をテナントに適用するには、左側のナビゲーション ウィンドウで **[テナント** ] を選択し、テナントを選択します。 次に、[展開計画] **タブに移動** して展開を開始します。

## <a name="lighthouse-baseline"></a>ライトハウスのベースライン

ライトハウスのベースライン構成は、すべての管理テナントが安全で準拠するように設計されています。 左側 **のナビゲーション ウィンドウ** から [基準計画] を選択して、すべてのテナントに適用される既定の基準計画を表示します。  既定の基準計画に含まれる展開手順を表示するには、[基準計画の表示] を選択 **して** 既定の基準計画ページを開きます。 展開の詳細とユーザーへの影響を表示するには、展開手順を選択します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="[既定の基準計画] ページのスクリーンショット。":::

### <a name="default-lighthouse-configurations"></a>既定のライトハウス構成

| ベースライン構成 | 説明 |
|--|--|
| 管理者に MFA を要求する | すべての管理者に対して多要素認証を必要とする条件付きアクセス ポリシー。 すべてのクラウド アプリケーションに必要です。 この基準の詳細については、「条件付きアクセス [: すべての管理者に MFA を要求する」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)。|
| エンド ユーザーに MFA を要求する | すべてのユーザーに対して多要素認証を必要とする条件付きアクセス ポリシー。  すべてのクラウド アプリケーションに必要です。 この基準の詳細については、「条件付きアクセス [: すべてのユーザーに MFA を要求する」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 |
| 従来の認証をブロックする | 従来のクライアント認証をブロックする条件付きアクセス ポリシー。 この基準の詳細については、「条件付きアクセスを使用して従来の[認証Azure ADをブロックする」を参照してください](/azure/active-directory/conditional-access/block-legacy-authentication)。|
| デバイスの登録を設定する | テナント デバイスがデバイスに登録できるデバイスMicrosoft エンドポイント マネージャー。 これは、ユーザーとユーザーの間で自動登録Azure Active Directory設定Microsoft エンドポイント マネージャー。 この基準の詳細については、「デバイスの登録を[設定する」をWindowsしてください](/mem/intune/enrollment/windows-enroll)。 |
| デバイスMicrosoft Defender ウイルス対策以降のWindows 10構成する | 事前に構成されたデバイスWindowsデバイスのデバイス構成プロファイルMicrosoft Defender ウイルス対策します。 この基準の詳細については、「 [Configure Microsoft Defender for Endpoint in Intune」を参照してください](/mem/intune/protect/advanced-threat-protection-configure)。|
| Microsoft Defender Firewall for Windows 10以降 | 望ましくないネットワーク トラフィックと承認されていないネットワーク トラフィックを防止してデバイスをセキュリティで保護するためのファイアウォール ポリシー。 この基準の詳細については、「ファイアウォールを構成するためのベスト プラクティス」[をWindows Defenderしてください](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。  |
| デバイス コンプライアンス ポリシーを構成して、Windows 10以降に設定する | 基本的Windows要件を満たす、事前に構成された設定を持つデバイス ポリシーです。 この基準の詳細については、「条件付きアクセス: 参加しているデバイスに準拠しているデバイスまたは[ハイブリッド Azure ADする」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。 |

## <a name="deployment-plans"></a>展開計画

アクティブな各テナントには、展開計画が含まれています。この計画には、Microsoft 365 Lighthouseがあります。 テナントの展開計画にアクセスするには、[テナント] ページの一覧からアクティブなテナントを選択し、[展開計画] タブ **を選択** します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/deployment-plan-tab.png" alt-text="[展開計画] タブのスクリーンショット。":::

[展開計画] タブには、次の情報が含まれています。


|列  |説明  |
|---------|---------|
|展開手順     |  展開手順の説明。       |
|状態     |展開手順の状態。         |
|基準     |展開手順の派生基準。         |
|カテゴリ     | 展開手順がデバイス、ID、またはデータの管理に関連付けられているかどうか。        |
|最終更新日時    | 展開手順が最後に更新された日付。        |


[展開計画] タブには、次のオプションも含まれています。

- **エクスポート:** 展開手順データをコンマ区切り値 (Excel) ファイルにエクスポート.csvします。
- **更新:** 最新の展開手順データを取得する場合に選択します。
- **検索:** キーワードを入力して、リスト内の特定の展開手順をすばやく見つける。

## <a name="deployment-steps-and-processes"></a>展開の手順とプロセス

各テナントの展開計画には、基本計画からの展開Microsoft 365 Lighthouse含まれています。 各展開手順は、展開手順の要件を満たすために完了する必要がある 1 つ以上のプロセスで構成されます。 新しいテナントがアクティブになったら、展開手順とプロセスに関連付けられた展開アクティビティを完了する必要があります。

展開手順ごとに、次のアクションを実行できます。

|アクション  |説明  |
|---------|---------|
| 共有    |  展開手順の内容をリンクまたは電子メールで共有できます。    |
| レビューと展開    |  ユーザーが次の操作を実行できます。 <ul><li>サポートされている場合は、テナントに設定を展開せずに、展開手順の構成設定と既存のポリシーの設定を比較します。<br>次の展開手順は、比較をサポートします。</br><ul><li>デバイス コンプライアンス ポリシーを構成して、Windows 10以降に設定する</li><li>エンド ユーザーに MFA を要求する</li><li>管理者に MFA を要求する</li><li>従来の認証をブロックする</li></ul></li> <li>構成設定をテナントに展開します。</li></ul>**注:** テナントに設定を展開せずに比較する機能をサポートしない手順を実行すると、構成設定を確認して展開できます。|
| アクション プランの状態を更新する    |  展開手順のアクション プランの状態をユーザーが報告できます。      |

## <a name="related-content"></a>関連コンテンツ

[ベースラインMicrosoft 365 Lighthouse展開](m365-lighthouse-deploy-baselines.md)する (記事)\
[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
