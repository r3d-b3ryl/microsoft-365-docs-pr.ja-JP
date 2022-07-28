---
title: Microsoft 365 Lighthouseベースラインを使用して標準テナント構成をデプロイする方法の概要
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: shcallaw, kywirpel
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、ベースラインを使用して標準テナント構成をデプロイする方法について説明します。
ms.openlocfilehash: 9261be531db428c3d081e87c6717dfc8710a5026
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67056638"
---
# <a name="overview-of-using-microsoft-365-lighthouse-baselines-to-deploy-standard-tenant-configurations"></a>Microsoft 365 Lighthouseベースラインを使用して標準テナント構成をデプロイする方法の概要 

Microsoft 365 Lighthouseベースラインは、複数の顧客テナント間で Microsoft 365 セキュリティ設定を管理するための反復可能でスケーラブルな方法を提供します。 ベースラインは、テナントのユーザー、デバイス、データのセキュリティを維持するコア セキュリティ ポリシーとコンプライアンス標準を展開する標準テナント構成を提供します。

既定のベースラインとその展開手順は、Lighthouse 内から確認できます。 テナントにベースラインを適用するには、左側のナビゲーション ウィンドウで **[テナント** ] を選択し、テナントを選択します。 次に、[ **展開計画]** タブに移動してデプロイを開始します。

## <a name="lighthouse-baseline"></a>ライトハウスベースライン

Lighthouse ベースライン構成は、すべてのマネージド テナントがセキュリティで保護され、準拠していることを確認するように設計されています。 左側のナビゲーション ウィンドウで [ **基準計画** ] を選択して、すべてのテナントに適用される既定のベースラインを表示します。 既定のベースラインに含まれるデプロイ手順を表示するには、[ **基準計画の表示** ] を選択して [ **既定のベースライン]** ページを開きます。 デプロイの詳細とユーザーへの影響を表示するには、デプロイ手順のいずれかを選択します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="[既定のベースライン] ページのスクリーンショット。":::

### <a name="default-lighthouse-configurations"></a>既定の Lighthouse 構成

| ベースライン構成 | 説明 |
|--|--|
| 管理者に MFA を要求する | すべての管理者に多要素認証を必要とする条件付きアクセス ポリシー。 これは、すべてのクラウド アプリケーションに必要です。 このベースラインの詳細については、「 [条件付きアクセス: すべての管理者に MFA を要求する」を](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)参照してください。|
| エンド ユーザーに MFA を要求する | すべてのユーザーに多要素認証を必要とする条件付きアクセス ポリシー。  これは、すべてのクラウド アプリケーションに必要です。 このベースラインの詳細については、「 [条件付きアクセス: すべてのユーザーに MFA を要求する」を](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)参照してください。 |
| 従来の認証をブロックする | レガシ クライアント認証をブロックする条件付きアクセス ポリシー。 このベースラインの詳細については、「 [条件付きアクセスを使用して Azure AD へのレガシ認証をブロックする](/azure/active-directory/conditional-access/block-legacy-authentication)」を参照してください。|
| デバイス登録を設定する | テナント デバイスが Microsoft エンドポイント マネージャーに登録できるようにするデバイス登録。 これは、Azure Active Directory と Microsoft エンドポイント マネージャーの間で自動登録を設定することによって行われます。 このベースラインの詳細については、「 [Windows デバイスの登録を設定する](/mem/intune/enrollment/windows-enroll)」を参照してください。 |
| Microsoft Defender for Businessを設定する | Microsoft Defender for Businessのテナントをプロビジョニングし、Microsoft エンドポイント マネージャーに既に登録されているデバイスをMicrosoft Defender for Businessにオンボードします。 詳細については、「[Microsoft Defender for Businessとは」](../security/defender-business/mdb-overview.md)を参照してください。 |
| Exchange Online ProtectionとMicrosoft Defender for Office 365を設定する | 推奨されるスパム対策、マルウェア対策、フィッシング詐欺対策、安全なリンク、安全な添付ファイル ポリシーをテナントExchange Onlineメールボックスに適用するポリシー。 |
| Windows 10 以降用に Microsoft Defender ウイルス対策を構成する | 事前に構成された Microsoft Defender ウイルス対策設定を持つ Windows デバイスのデバイス構成プロファイル。 このベースラインの詳細については、「[IntuneでMicrosoft Defender for Endpointを構成する](/mem/intune/protect/advanced-threat-protection-configure)」を参照してください。|
| Windows 10 以降のMicrosoft Defender ファイアウォールを構成する | 不要で承認されていないネットワーク トラフィックを防ぐことでデバイスをセキュリティで保護するためのファイアウォール ポリシー。 このベースラインの詳細については、「[Windows Defender ファイアウォールを構成するためのベスト プラクティス」](/windows/security/threat-protection/windows-firewall/best-practices-configuring)を参照してください。  |
| Windows 10 以降のデバイス コンプライアンス ポリシーを構成する | 基本的なコンプライアンス要件を満たすために事前に構成された設定を持つ Windows デバイス ポリシー。 このベースラインの詳細については、「 [条件付きアクセス: 準拠またはハイブリッドの Azure AD 参加済みデバイスを必要とする](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)」を参照してください。 |

## <a name="deployment-plans"></a>展開計画

アクティブな各テナントには、Microsoft 365 Lighthouse ベースラインからのデプロイ手順を含むデプロイ 計画があります。 テナントの展開計画にアクセスするには、[テナント] ページの一覧からアクティブな **テナント** を選択し、[ **展開計画** ] タブを選択します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/deployment-plan-tab.png" alt-text="[展開計画] タブのスクリーンショット。":::

[展開計画] タブには、次の情報が含まれています。


|列  |説明  |
|---------|---------|
|デプロイ手順     |  展開手順の説明。       |
|状態     |デプロイ 手順の状態。         |
|基準     |デプロイ ステップの派生元となるベースライン。         |
|カテゴリ     | 展開手順がデバイス、ID、またはデータの管理に関連付けられているかどうか。        |
|最終更新日時    | デプロイ ステップが最後に更新された日付。        |


[展開計画] タブには、次のオプションも含まれています。

- **エクスポート：** デプロイ ステップ データを Excel コンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **更新：** 最新のデプロイ ステップ データを取得する場合に選択します。
- **検索：** キーワードを入力して、一覧内の特定のデプロイ ステップをすばやく見つけます。

## <a name="deployment-steps-and-processes"></a>デプロイの手順とプロセス

各テナントのデプロイ計画には、Microsoft 365 Lighthouseベースラインからのデプロイ手順が含まれます。 各デプロイ 手順には、完了する必要がある 1 つ以上のプロセスが含まれます。 新しいテナントがアクティブになったら、デプロイの手順とプロセスに関連付けられたデプロイ アクティビティを完了する必要があります。

デプロイ手順ごとに、次のアクションを実行できます。

|アクション  |説明  |
|---------|---------|
| 共有    |  展開手順の内容をリンクまたは電子メールで共有できるようにします。    |
| 確認とデプロイ    |  ユーザーは次の操作を行うことができます。 <ul><li>サポートされている場合は、テナントに設定を展開せずに、展開手順の構成設定と既存のポリシーの設定を比較します。<br>次のデプロイ手順では、比較がサポートされています。</br><ul><li>Windows 10 以降のデバイス コンプライアンス ポリシーを構成する</li><li>エンド ユーザーに MFA を要求する</li><li>管理者に MFA を要求する</li><li>従来の認証をブロックする</li></ul></li> <li>構成設定をテナントにデプロイします。</li></ul>**メモ：** テナントに設定を展開せずに比較する機能をサポートしていない手順を使用すると、構成設定を確認して展開できます。|
| アクション プランの状態を更新する    |  ユーザーが展開手順のアクション プランの状態を報告できるようにします。      |

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseベースラインをデプロイする](m365-lighthouse-deploy-baselines.md) (記事)\
[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
