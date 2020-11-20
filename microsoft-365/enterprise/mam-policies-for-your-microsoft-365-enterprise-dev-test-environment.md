---
title: Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境に Intune デバイスコンプライアンスポリシーを追加します。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367097"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

この記事では、Windows 10 365 デバイスの Intune デバイスコンプライアンスポリシーを Microsoft 365 for enterprise テスト環境に追加する方法について説明します。

Intune デバイスコンプライアンスポリシーを追加するには、次の2つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で MAM ポリシーを構成する場合は、「 [簡易基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する

このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。 このフェーズでは、Microsoft Intune と [Microsoft エンドポイント管理センター](https://go.microsoft.com/fwlink/?linkid=2109431) を使用して、グループを追加し、コンプライアンスポリシーを作成します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、全体管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。 **エンドポイントマネージャー** 管理センターを選択します。 [エンドポイントマネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)が開きます。

    [デバイス管理] が [ **有効になってい** ません] というメッセージが表示されている場合は、MDM authority として [Intune] を選択します。 具体的な手順については、「 [モバイルデバイス管理機関を設定する](/mem/intune/fundamentals/mdm-authority-set)」を参照してください。

    エンドポイントマネージャー管理センターは、デバイスの管理とアプリの管理に重点を置いています。 この管理センターのツアーについては、「 [チュートリアル: Microsoft エンドポイントマネージャーのチュートリアル Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)」を参照してください。

2. [**グループ**] で、メンバーシップの種類が **割り当てられ** た、新しい **Microsoft 365** または **Managed Windows 10 デバイスユーザー** という名前の **セキュリティ** グループを追加します。 次の手順では、コンプライアンスポリシーをこのグループに割り当てます。 

    特定の手順、および **マイクロソフトの 365** または **セキュリティ** グループの詳細については、「 [ユーザーとデバイスを整理するためにグループを追加する](/mem/intune/fundamentals/groups-add)」を参照してください。

3. [ **デバイス**] で、Windows 10 コンプライアンスポリシーを作成します。 作成した **管理 Windows 10 デバイスユーザー** グループにこのポリシーを割り当てます。

    ポリシーでは、単純なパスワードをブロックしたり、ファイアウォールを必要としたり、Microsoft Defender マルウェア対策サービスを実行する必要があります。 通常、コンプライアンスポリシーには、すべてのデバイスに必要な基本設定、または最小限の要件が含まれています。

    具体的な手順、および構成できるコンプライアンス設定の詳細については、「 [コンプライアンスポリシーを使用して、管理するデバイスのルールを設定する](/mem/intune/protect/device-compliance-get-started)」を参照してください。

完了したら、管理された **Windows 10 デバイスユーザー** グループのメンバーをテストするためのデバイスコンプライアンスポリシーが用意されています。
  
## <a name="next-step"></a>次の手順

テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。
  
[Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
