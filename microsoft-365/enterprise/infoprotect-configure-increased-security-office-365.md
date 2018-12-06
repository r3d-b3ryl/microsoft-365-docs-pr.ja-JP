---
title: '手順 3: Office 365 のセキュリティ強化を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 (Office 365 ATP を含む) のセキュリティ強化について理解し、構成します。
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869525"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>手順 3: Office 365 のセキュリティ強化を構成する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 サブスクリプションとそのデータが、最初から悪意のある脅威から保護されているようにするには、「[セキュリティ強化のために Office 365 テナントを構成する](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)」を参照し、次の追加セキュリティを構成します。

- Office 365 セキュリティ/コンプライアンス センターの脅威管理ポリシー
- その他の Exchange Online テナント レベルの設定
- SharePoint 管理センターでのテナント レベルでの共有ポリシー
- Azure Active Directory の設定

構成が完了したら、セキュリティ状態に関する情報を次のソースから入手できます。

- セキュリティ センターとコンプライアンス センターのダッシュボードとレポート
- [Office 365 セキュリティ スコア](https://securescore.office.com/)
 
  このページにアクセスするには、Office 365 テナント管理者としてサインインする必要があります。

Cloud App Security または Office 365 Cloud App Security を使用してセキュリティ イベントとセキュリティ活動を監視することもできます。詳細については、「[Office 365 Cloud App Security の概要](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)」を参照してください。

その他のセキュリティ機能として、Office 365 Advanced Threat Protection (ATP) があります。ATP は、次の処理により組織の共同作業のセキュリティを強化します。

- メールの添付ファイルやリンクを保護する。 
- Exchange Online のメールと、SharePoint Online、OneDrive for Business、Microsoft Teams のドキュメントに対し、スプーフィング インテリジェンスとフィッシング対策機能を提供する 

>[!Note]
>Office 365 ATP は Microsoft 365 Enterprise E5 に含まれています。Microsoft 365 Enterprise E3 を使用している場合は、ATP の個別ライセンスを購入できます。
>

Office 365 ATP を有効にするには、「[SharePoint Online、OneDrive for Business、Microsoft Teams の Office 365 Advanced Threat Protection を有効にする](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)」を参照してください。

詳細については、「[SharePoint、OneDrive、マイクロソフトのチーム用の office 365 の分析ツール](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)」を参照してください。


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Office 365 のセキュリティ強化を構成する](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)を確認できます。

## <a name="next-step"></a>次の手順


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[特権アクセス管理を構成する](infoprotect-configure-privileged-access-management.md)|


