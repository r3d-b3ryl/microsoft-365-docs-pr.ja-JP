---
title: '手順 3: Microsoft 365 のセキュリティ強化を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 のセキュリティ強化を理解して、構成します。
ms.openlocfilehash: 290b10dd8e0bf9a7180bae72669b22f3d575f914
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370174"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a>手順 3: Microsoft 365 のセキュリティ強化を構成する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Microsoft 365 サブスクリプションとそのデータが、悪意のある脅威から最初から保護されているようにするには、次を構成します。

- [脅威管理ポリシーの調整](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [その他の Exchange Online テナント レベルの設定](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [SharePoint 管理センターでのテナント レベルでの共有ポリシー](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [Azure Active Directory (Azure AD) の設定](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

構成が完了したら、セキュリティ状態に関する情報を次のソースから入手できます。

- [Microsoft セキュリティ センターのダッシュボードとレポート](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [Microsoft セキュア スコア](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

その他のセキュリティ機能として、[Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) があります。ATP は、次の処理により組織の共同作業のセキュリティを強化します。

- メールの[リンク](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)と[添付ファイル](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)を保護する。 
- Exchange Online のメールと、[SharePoint Online、OneDrive for Business、Microsoft Teams のファイル](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)に対し、スプーフィング インテリジェンスとフィッシング対策機能を提供する。 

Office 365 ATP は、Microsoft 365 Enterprise E5 でのみ利用可能です。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Microsoft 365 のセキュリティ強化を構成する](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)を確認できます。

## <a name="next-step"></a>次の手順


|||
|:-------|:-----|
|![手順 4](./media/stepnumbers/Step4.png)|[Windows 情報保護を構成する](infoprotect-deploy-windows-information-protection.md)|


