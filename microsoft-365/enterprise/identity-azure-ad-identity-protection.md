---
title: '手順 6: 資格情報が侵害されないように保護する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Identity Protection について理解し、構成します。
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869643"
---
# <a name="step-6-protect-against-credential-compromise"></a>手順 6: 資格情報が侵害されないように保護する

*この手順はオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、資格情報を侵害から保護するポリシーを構成する方法を説明します。資格情報の侵害では、攻撃者がユーザーのアカウント名とパスワードを把握し、組織のクラウド サービスとデータへのアクセスを獲得します。Azure AD Identity Protection には、攻撃者によるアカウントやグループ間の水平移動と、その後の最も価値の高いデータへの移動を防止するための手段が多数あります。

Azure AD Identity Protection では次の作業を実行できます。

|||
|:---------|:---------|
|組織の ID における潜在的な脆弱性の洗い出しと対処|Azure AD では、機械学習を使用して異常や不審なアクティビティ (サインインとサインイン後の活動など) を検出します。Identity Protection はこのデータを使用して、問題の評価と対処の実施に役立つレポートとアラートを生成します。|
|組織の ID に関連する不審なアクションの検出と自動対応|指定されているリスク レベルに達した時点で、検出された問題に対し自動的に対応するリスクベースのポリシーを構成できます。このリスクベースのポリシーと、Azure Active Directory および Enterprise Mobility + Security (EMS) の他の条件付きアクセス制御との組み合わせにより、自動的にアクセスをブロックするか、または修正処置 (パスワード リセットと後続のサインインでの多要素認証の義務付けなど) を実行することができます。|
|不審なインシデントを調査し、管理操作によって解決する|セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。|

[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。

[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。

この手順の結果として、Azure AD Identity Protection が有効になり、次の目的で Azure AD Identity Protection を使用できるようになります。

- 潜在的な ID の脆弱性に対処する。
- 資格情報の侵害の疑いがあるものを検出する。
- 発生している不審な ID インシデントを調査して対処する。

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-ident-prot)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [ディレクトリを同期する](identity-azure-ad-connect.md) |


