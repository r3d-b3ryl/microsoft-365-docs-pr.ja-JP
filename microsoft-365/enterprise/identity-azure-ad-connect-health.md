---
title: '手順 8: 同期の状態を監視する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Connect Health について理解し、構成します。
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869421"
---
# <a name="step-8-monitor-synchronization-health"></a>手順 8: 同期の状態を監視する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、Azure AD Connect Health エージェントを各オンプレミス ID サーバーにインストールし、ID インフラストラクチャと Azure AD Connect から提供される同期サービスを監視します。監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。

![Azure AD Connect Health のコンポーネント](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。

- **管理認証**オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。
- Active Directory フェデレーション サービス (AD FS) で**フェデレーション認証**を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。

この手順の完了後の成果物は次のとおりです。

- Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。
- Azure AD Connect Health ポータルに、オンプレミス インフラストラクチャの現在の状態と、Office 365 および EMS サブスクリプションの Azure AD テナントとの同期アクティビティが表示される。

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-sync-health)を確認できます。


## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [パスワードの更新を簡素化する](identity-password-writeback.md) |

