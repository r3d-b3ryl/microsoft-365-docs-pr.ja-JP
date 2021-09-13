---
title: エンタープライズ テストMicrosoft 365のセキュリティMicrosoft 365強化
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境Microsoft 365セキュリティ設定Microsoft 365を有効にします。
ms.openlocfilehash: 7598ade331ae340ede52f4c47375aebba792eb84
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216003"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テストMicrosoft 365のセキュリティMicrosoft 365強化

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

この記事の手順では、エンタープライズ テスト環境Microsoft 365セキュリティを強化するために、Microsoft 365設定を構成します。

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小限の要件で軽量な方法でMicrosoft 365のセキュリティを構成する場合は、「Lightweight 基本構成」の手順[に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズでセキュリティMicrosoft 365を構成する場合は、「パススルー認証」[の手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> セキュリティのMicrosoft 365テストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 これはオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>フェーズ 2: セキュリティの強化Microsoft 365構成する

このフェーズでは、エンタープライズ テスト環境Microsoft 365セキュリティMicrosoft 365強化します。 詳細と設定については、「セキュリティ強化 [のためにテナントを構成する」を参照してください](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>最新SharePointをサポートしないアプリをブロックするオンラインの構成

最新の認証をサポートしていないアプリには、ID とデバイス アクセス構成を適用できません。これは、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティ保護する重要な要素です。 [](../security/office-365-security/microsoft-365-policies-configurations.md) 

1. [管理者] に<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>し、グローバル管理者アカウントMicrosoft 365テスト ラボ サブスクリプションにサインインします。
    
  - 軽量のテスト環境を使用しているMicrosoft 365ローカル コンピューターからサインインします。
    
  - テスト環境でシミュレートされたエンタープライズ Microsoft 365を使用している場合は[、Azure portal](https://portal.azure.com)を使用して CLIENT1 仮想マシンに接続し、CLIENT1 からサインインします。
 
2. [新しい **ナビゲーション** Microsoft 365 管理センター] タブの左側のナビゲーション ウィンドウ **の**[管理センター] で、[**管理]** をクリックSharePoint。
3. [管理センター]**タブSharePoint[** ポリシー] をクリックし、[アクセス **>] をクリックします**。
4. [ **モダン認証をサポートしないアプリ] をクリックし**、[ **アクセスをブロック** する] を選択し、[保存] を **クリックします**。


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>[Defender for Office 365] SharePoint、OneDrive for Business、およびMicrosoft Teams

Defender for Office 365、SharePoint、OneDrive、Microsoft Teamsファイルを誤って共有する組織を保護します。

1. コンプライアンス センターの [セキュリティ &に移動し](https://protection.office.com) 、グローバル管理者アカウントでサインインします。

2. 左側のナビゲーション ウィンドウの [脅威の管理] で **、[ポリシー**] をクリックし、[添付ファイルセーフ **クリックします**。 

3. [**ファイルの保護] SharePoint、OneDrive、およびMicrosoft Teams。** [ATP **を有効にする] をSharePoint、OneDrive、およびMicrosoft Teams**。

4. **[保存]** をクリックします。


### <a name="enable-anti-malware"></a>マルウェア対策を有効にする

マルウェアは、ウイルスとスパイウェアから構成されます。 ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。 スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。 

Microsoft 365には、悪意のあるソフトウェアから受信メッセージと送信メッセージを保護し、スパムから保護するのに役立つ組み込みのマルウェアおよびスパム フィルター機能があります。 詳細については、「スパム対策 [とマルウェア対策&を参照してください](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。

一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が実行されるのを確認するには、次の手順を実行します。

1. ブラウザーの [戻る] ボタンをクリックして、[ポリシー] ページに **戻** ります。
2. [マルウェア **対策] をクリックします**。
3. Default という名前のポリシーを **ダブルクリックします**。
4. [マルウェア対策 **ポリシー] ウィンドウで、[** 削除]**をクリック設定。**
4. [共通 **の添付ファイルの種類] フィルターで**、[オン] **を** 選択し、[保存] を **クリックします**。


## <a name="phase-3-examine-the-security-dashboard"></a>フェーズ 3: セキュリティ ダッシュボードを調べる

Microsoft 365 の脅威管理は、組織のデータへのモバイル デバイス アクセスを制御および管理し、データ損失から組織を保護し、悪意のあるソフトウェアやスパムから受信および送信メッセージを保護するのに役立ちます。 また、脅威管理を使用して、ドメインの評判を保護し、送信者がドメインからアカウントを悪意を持ってスプーフィングするかどうかを判断します。 

セキュリティ ダッシュボードを表示するには、次の方法を実行します。

1. 必要に応じて、コンプライアンス センターの [セキュリティ &に移動](https://protection.office.com) し、グローバル管理者アカウントでサインインします。

2. 左側のナビゲーション ウィンドウの [脅威の管理] **で、[ダッシュボード**] を **クリックします**。

ダッシュボードのすべてのカードを詳しくは、提供された情報を理解してください。

詳細については、「セキュリティ ダッシュボード [」を参照してください](../security/office-365-security/security-dashboard.md)。


## <a name="phase-4-examine-microsoft-secure-score"></a>フェーズ 4: Microsoft Secure Score を調べる

Microsoft Secure Score は、サブスクリプションで利用可能な機能に対する現在のレベルを示す、セキュリティの姿勢を数値で示します。 また、スコアを向上させるために実行できる改善アクションの一覧も表示されます。

1. ブラウザーで新しいタブを作成し、セキュリティ センターのMicrosoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">に</a>移動し、[スコアのセキュリティ保護]**をクリックします**。
2. [概要 **] タブ**  で、現在の Secure Score と、それがグローバル平均とサブスクリプションと同じ数のライセンスと比較する方法をメモします。
3. [改善アクション **] タブ** で、スコアを上げするために実行できるアクションの一覧を確認します。

詳細については [、「Microsoft Secure Score」を参照してください](../security/defender/microsoft-secure-score.md)。

## <a name="next-steps"></a>次の手順

テスト環境 [の追加情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)