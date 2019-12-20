---
title: Microsoft 365 エンタープライズテスト環境の Microsoft 365 セキュリティの強化
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、microsoft 365 エンタープライズテスト環境で追加の Microsoft 365 セキュリティ設定を有効にします。
ms.openlocfilehash: 8e8e05f223faedd60ea53683b3531964b3220291
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801692"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 エンタープライズテスト環境の Microsoft 365 セキュリティの強化

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

この記事の手順に従って、Microsoft 365 エンタープライズテスト環境のセキュリティを強化するために、その他の Microsoft 365 設定を構成します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件での軽量な方法で、強化された Microsoft 365 セキュリティを構成するだけの場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで、強化された Microsoft 365 セキュリティを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。
  
> [!NOTE]
> Microsoft 365 セキュリティのテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズテスト環境を必要としません。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>フェーズ 2: Microsoft 365 のセキュリティ強化を構成する

このフェーズでは、Microsoft 365 エンタープライズテスト環境に対して、強化された Microsoft 365 セキュリティを有効にします。 その他の詳細と設定については、「 [Configure Your Office 365 tenant for security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)」を参照してください。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>先進認証をサポートしていないアプリをブロックするように SharePoint Online を構成する

モダン認証をサポートしていないアプリには、 [id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)を適用できません。これは、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティ保護するための重要な要素です。 

1. Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動し、全体管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。
    
  - ライトウェイトの Microsoft 365 テスト環境を使用している場合は、ローカルコンピューターからサインインします。
    
  - シミュレートされたエンタープライズ Microsoft 365 テスト環境を使用している場合は、 [Azure portal](https://portal.azure.com)を使用して client1 仮想マシンに接続し、client1 からサインインします。
 
2. 新しい**Microsoft 365 管理センター**のタブで、左側のナビゲーションウィンドウの [**管理センター** ] の下にある [ **SharePoint**] をクリックします。
3. [新しい**SharePoint 管理センター** ] タブで、[**アクセス制御**] をクリックします。
4. [**モダン認証をサポートしていないアプリ**] をクリックし、[**アクセスをブロック**する] を選択して、[**保存**] をクリックします。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>SharePoint、OneDrive for Business、Microsoft Teams の Advanced Threat Protection を有効にする

Office 365 Advanced Threat Protection (ATP) for SharePoint、OneDrive、Microsoft Teams は、悪意のあるファイルを誤って共有することから組織を保護します。

1. [Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動し、全体管理者アカウントでサインインします。

2. 左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ポリシー**] をクリックし、[ATP の**安全な添付ファイル**] をクリックします。 

3. [ **SharePoint、OneDrive、Microsoft Teams のファイルを保護**する] で。 [ **SharePoint、OneDrive、Microsoft Teams に対して ATP を有効にする**] を選択します。

4. [**保存**] をクリックします。


### <a name="enable-anti-malware"></a>マルウェア対策を有効にする

マルウェアは、ウイルスとスパイウェアから構成されます。 ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。 スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。 

Microsoft 365 には、受信および送信メッセージを悪意のあるソフトウェアから保護し、スパムから保護するのに役立つ、組み込みのマルウェアおよびスパムフィルタリング機能が用意されています。 詳細については、「 [Office のスパム対策 & マルウェア対策保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)」を参照してください365

一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が実行されることを確認するには、次のようにします。

1. ブラウザーの [戻る] ボタンをクリックすると、[**ポリシー** ] ページに戻ります。
2. [**マルウェア対策**] をクリックします。
3. **Default**という名前のポリシーをダブルクリックします。
4. [**マルウェア対策ポリシー** ] ウィンドウで、[**設定**] をクリックします。
4. [**一般的な添付ファイルの種類のフィルター**] で、 **[オン] を選択し**、[**保存**] をクリックします。


## <a name="phase-3-examine-the-security-dashboard"></a>フェーズ 3: セキュリティダッシュボードを検証する

Office 365 の脅威管理は、組織のデータへのモバイルデバイスアクセスの制御と管理、データ損失からの組織の保護、および悪意のあるソフトウェアとスパムからの受信および送信メッセージの保護に役立ちます。 また、脅威管理を使用して、ドメインの評価を保護し、送信者が悪意のあるドメインからのアカウントを偽装しているかどうかを判断します。 

セキュリティダッシュボードを表示するには、次のようにします。

1. 必要に応じて、 [Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動し、全体管理者アカウントでサインインします。

2. 左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ダッシュボード**] をクリックします。

ダッシュボードのすべてのカードをよく見て、提供されている情報について理解してください。

詳細については、「 [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)」を参照してください。


## <a name="phase-4-examine-microsoft-secure-score"></a>フェーズ 4: Microsoft のセキュリティで保護されたスコアを調べる

Microsoft Secure Score は、お客様のサブスクリプションで利用可能な機能に対する現在のレベルを示す数値として、セキュリティの姿勢を示します。 また、スコアを向上させるために実行できる改善アクションの一覧も提供します。

1. ブラウザーで新しいタブを作成し、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/)に移動して、[**セキュリティで保護されたスコア**] をクリックします。
2. [**概要**] タブで、現在のセキュリティスコアと、それが同じ数のライセンスを持つグローバルな平均およびサブスクリプションと比較されることに注意してください。
3. [**改善アクション**] タブで、スコアを増やすために実行できるアクションの一覧を確認します。

詳細については、「 [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)」を参照してください。

## <a name="next-steps"></a>次のステップ

これらの設定を運用環境で構成する情報およびリンクについては、**情報保護**フェーズの「 [365 Microsoft のセキュリティを構成](infoprotect-configure-increased-security-office-365.md)する」の手順を参照してください。

テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
