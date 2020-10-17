---
title: Microsoft 365 for enterprise テスト環境の Azure AD Id 保護
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、Microsoft 365 for enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487710"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境の Azure AD Id 保護

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

Azure Active Directory (Azure AD) Id 保護を使用して、組織の id に影響する可能性のある潜在的な脆弱性を検出したり、自動化された応答を構成したり、インシデントを調査したりできます。 この記事では、Azure AD Identity Protection を使用して、テスト環境アカウントの分析を表示する方法について説明します。

Microsoft 365 のエンタープライズテスト環境で Azure AD Id 保護をセットアップするには、次の2つのフェーズが必要です。

- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Azure AD Identity Protection を使用する](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で Azure AD Identity Protection のみをテストする場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> Azure AD Identity Protection をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 これは、Azure AD Id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>フェーズ 2: Azure AD Identity Protection を使用する

1. ブラウザーのプライベートインスタンスを開き、 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 for enterprise テスト環境のグローバル管理者アカウントを使用して、Azure portal にサインインします。
2. Azure portal で、検索ボックスに「 **id 保護** 」と入力し、[ **Azure AD id 保護**] を選択します。
3. [ **Identity Protection-概要** ] ブレードで、各レポートを選択してレポートの詳細を確認します。
4. [ **通知**] の下で、[ **リスクが検出されたアラート**] を選択します。
5. [ **リスクが検出されたユーザーのアラート** ] ウィンドウで、[ **中**] を選択します。
6. **メールが次のユーザーに送信さ**れる場合は、[**含める**] を選択して、グローバル管理者アカウントが選択されているメンバーの一覧に含まれていることを確認します。
7. [**保存**] を選択します。

[ **保護**] で、さまざまなポリシーを選択して、それらを構成する方法を確認します。 ポリシーを作成してアクティブにした場合は、すべてのユーザーのアクセスがブロックされていないこと、またはサインインできないことを確認してください。 これを防ぐには、グローバル管理者など、特定のユーザーアカウントを除外します。

テストと実験の詳細については、「 [リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
