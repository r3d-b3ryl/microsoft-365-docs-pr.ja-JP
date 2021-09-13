---
title: 基準計画を使用した標準テナント構成の展開の概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseを使用して標準的なテナント構成を展開する方法について説明します。
ms.openlocfilehash: 5dc1f7da329ab1630d857ee337048a47ad06c9e9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191140"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>基準計画を使用した標準テナント構成の展開の概要 

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouse基準は、複数の顧客テナント間でセキュリティ設定を評価および管理するためのMicrosoft 365スケーラブルな方法を提供します。 ベースラインは、ユーザー、デバイス、およびデータをセキュリティで保護する構成を使用して、コア セキュリティ ポリシーとテナントコンプライアンス標準を監視するのにも役立ちます。

パートナーが独自のペースでセキュリティを導入するのに役立つ目的で設計されたライトハウスは、標準のベースライン パラメーターと、サービスの事前定義された構成Microsoft 365提供します。 これらのセキュリティ構成は、テナントのセキュリティとコンプライアンスMicrosoft 365を測定するのに役立ちます。

既定の基準計画とその展開手順は、ライトハウス内から表示できます。 テナントにベースラインを適用するには、左側のナビゲーション ウィンドウ **で [テナント** ] を選択し、テナントを選択します。 次に、[展開計画] **タブに移動** し、目的の基準計画を実装します。

## <a name="standard-baseline-security-templates"></a>標準の基準計画のセキュリティ テンプレート

セキュリティ ワークロードのライトハウス標準ベースライン構成は、すべての管理テナントが許容可能なセキュリティ範囲とコンプライアンス状態に達するように設計されています。

次の表のベースライン構成には、ライトハウスの既定の基準計画が標準で示されています。<br><br>

| ベースライン構成 | 説明 |
|--|--|
| 管理者に MFA を要求する | 管理者に多要素認証を必要とするレポート専用の条件付きアクセス ポリシー。 すべてのクラウド アプリケーションに必要です。 |
| エンド ユーザーに MFA を要求する | ユーザーに多要素認証を必要とするレポート専用の条件付きアクセス ポリシー。 すべてのクラウド アプリケーションに必要です。 |
| 従来の認証をブロックする | レガシ クライアント認証をブロックするレポート専用の条件付きアクセス ポリシー。 |
| デバイスをデバイスに登録Microsoft エンドポイント マネージャー – Azure AD参加 | テナント デバイスがデバイスに登録できるデバイスMicrosoft エンドポイント マネージャー。 これは、ユーザーとユーザーの間で自動登録Azure Active Directory設定Microsoft エンドポイント マネージャー。 |
| ウイルス対策 (AV) ポリシーの構成 | 構成済みのデバイスWindowsデバイスのデバイス構成プロファイルMicrosoft Defender ウイルス対策します。 |
| ウィンドウ 10 コンプライアンス ポリシーのセットアップ | 基本的Windows要件を満たす、事前に構成された設定を持つデバイス ポリシーです。 |

## <a name="related-content"></a>関連コンテンツ

[ベースラインMicrosoft 365 Lighthouse展開](m365-lighthouse-deploy-baselines.md)する (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
