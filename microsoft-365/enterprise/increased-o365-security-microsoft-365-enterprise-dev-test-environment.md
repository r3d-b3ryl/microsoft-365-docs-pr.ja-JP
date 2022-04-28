---
title: エンタープライズ テスト環境のMicrosoft 365のMicrosoft 365セキュリティの強化
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
- admindeeplinkSPO
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境でMicrosoft 365追加のMicrosoft 365セキュリティ設定を有効にします。
ms.openlocfilehash: 4c69fadd3fb3e6744fad850e76282ea2339f48ee
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100723"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365のMicrosoft 365セキュリティの強化

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

この記事の手順では、エンタープライズ テスト環境のMicrosoft 365のセキュリティを向上させるために、追加のMicrosoft 365設定を構成します。

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小限の要件で軽量な方法でMicrosoft 365セキュリティの強化を構成する場合は、「[Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズでセキュリティの強化Microsoft 365を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> セキュリティの強化Microsoft 365テストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、自動化されたライセンスとグループ メンバーシップをテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>フェーズ 2: セキュリティの強化Microsoft 365構成する

このフェーズでは、エンタープライズ テスト環境のMicrosoft 365のMicrosoft 365セキュリティを強化します。 その他の詳細と設定については、「 [セキュリティを強化するためにテナントを構成する」を参照してください](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>最新の認証をサポートしていないアプリをブロックするようにオンラインSharePoint構成する

先進認証をサポートしていないアプリには[、ID とデバイス アクセスの構成](../security/office-365-security/microsoft-365-policies-configurations.md)を適用することはできません。これは、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティで保護する重要な要素です。 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>に移動し、グローバル管理者アカウントを使用してMicrosoft 365テスト ラボ サブスクリプションにサインインします。
    
  - 軽量Microsoft 365テスト環境を使用している場合は、ローカル コンピューターからサインインします。
    
  - シミュレートされたエンタープライズ Microsoft 365 テスト環境を使用している場合は、[Azure portal](https://portal.azure.com)を使用して CLIENT1 仮想マシンに接続し、CLIENT1 からサインインします。
 
2. 新しい **[Microsoft 365 管理センター**] タブの左側のナビゲーション ウィンドウの [**管理センター**] で、[**SharePoint**] をクリックします。
3. 新しい **SharePoint管理センター** タブで、**PoliciesAccess コントロールを** > 選択します。<a href="https://go.microsoft.com/fwlink/?linkid=2185071" target="_blank"></a>
4. **[先進認証をサポートしていないアプリ**] を選択し、[**アクセスのブロック**] を選択して、[保存] を選択 **します**。


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>SharePoint、OneDrive for Business、Microsoft TeamsのDefender for Office 365を有効にする

SharePoint、OneDrive、Microsoft TeamsのDefender for Office 365は、悪意のあるファイルを誤って共有しないように組織を保護します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">セキュリティ & コンプライアンス センター</a>に移動し、グローバル管理者アカウントでサインインします。

2. 左側のナビゲーション ウィンドウの [**脅威の管理**] で[**ポリシー**]、[**添付ファイルのセーフ**] の順にクリックします。 

3. [**SharePoint、OneDrive、およびMicrosoft Teams内のファイルを保護** する] の下にあります。 **[SharePoint、OneDrive、Microsoft Teamsの ATP を有効にする**] を選択します。

4. **[保存]** をクリックします。


### <a name="enable-anti-malware"></a>マルウェア対策を有効にする

マルウェアは、ウイルスとスパイウェアから構成されます。 ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。 スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。 

Microsoft 365には、悪意のあるソフトウェアから受信メッセージと送信メッセージを保護し、スパムから保護するのに役立つマルウェアとスパムフィルター機能が組み込まれています。 詳細については、「 [スパム対策&マルウェア対策の保護](../security/office-365-security/anti-spam-and-anti-malware-protection.md)」を参照してください。

一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が確実に実行されるようにするには、次の手順を実行します。

1. ブラウザーの [戻る] ボタンをクリックして、[ **ポリシー** ] ページに戻ります。
2. [ **マルウェア対策**] をクリックします。
3. 既定という名前のポリシーをダブルクリック **します**。
4. [**マルウェア対策ポリシー**] ウィンドウで、[**設定**] をクリックします。
4. **[一般的な添付ファイルの種類] フィルター** で [**オン**] を選択し、[**保存**] をクリックします。


## <a name="phase-3-examine-the-security-dashboard"></a>フェーズ 3: セキュリティ ダッシュボードを調べる

Microsoft 365の脅威管理は、組織のデータへのモバイル デバイス アクセスを制御および管理し、データ損失から組織を保護し、悪意のあるソフトウェアやスパムから受信メッセージと送信メッセージを保護するのに役立ちます。 また、脅威管理を使用して、ドメインの評判を保護し、送信者がドメインのアカウントを悪意を持ってスプーフィングしているかどうかを判断します。 

セキュリティ ダッシュボードを表示するには:

1. 必要に応じて、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">セキュリティ & コンプライアンス センター</a> に移動し、グローバル管理者アカウントでサインインします。

2. 左側のナビゲーション ウィンドウの [ **脅威の管理**] で、[ **ダッシュボード**] をクリックします。

ダッシュボード上のすべてのカードをよく見て、提供された情報を理解してください。

詳細については、「 [セキュリティ ダッシュボード](../security/office-365-security/security-dashboard.md)」を参照してください。


## <a name="phase-4-examine-microsoft-secure-score"></a>フェーズ 4: Microsoft セキュリティ スコアを調べる

Microsoft Secure Score では、セキュリティ体制が数値として表示されます。これは、サブスクリプションで使用可能な機能に対する現在のレベルを示します。 また、スコアを向上させるために実行できる改善アクションの一覧も表示されます。

1. ブラウザーで新しいタブを作成し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動して、[**セキュリティで保護されたスコア**] をクリックします。
2. [ **概要**  ] タブで、現在のセキュア スコアと、それがグローバル平均と比較される方法と、同様の数のライセンスを持つサブスクリプションに注目します。
3. [ **改善アクション** ] タブで、スコアを上げるために実行できるアクションの一覧を確認します。

詳細については、 [Microsoft セキュリティ スコア](../security/defender/microsoft-secure-score.md)に関するページを参照してください。

## <a name="next-steps"></a>次の手順

テスト環境の [追加情報保護機能](m365-enterprise-test-lab-guides.md#information-protection) と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
