---
title: エンタープライズ テスト環境のMicrosoft 365のデバイス コンプライアンス ポリシー
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境のMicrosoft 365にIntuneデバイス コンプライアンス ポリシーを追加します。
ms.openlocfilehash: 3037ca846fe74fb8de51c78799e69c510821a034
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099457"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365のデバイス コンプライアンス ポリシー

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

この記事では、Windows 10 デバイスとMicrosoft 365 Apps for enterpriseのIntune デバイス コンプライアンス ポリシーをエンタープライズ テスト環境のMicrosoft 365に追加する方法について説明します。

Intune デバイス コンプライアンス ポリシーの追加には、次の 2 つのフェーズがあります。
- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Windows 10 デバイスのデバイス コンプライアンス ポリシーを作成する](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を持つ軽量な方法でのみ MAM ポリシーを構成する場合は、「 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスとグループ メンバーシップのテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、自動化されたライセンスとグループ メンバーシップをテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: Windows 10 デバイスのデバイス コンプライアンス ポリシーを作成する

このフェーズでは、Windows 10 デバイスのデバイス コンプライアンス ポリシーを作成します。 このフェーズでは、Microsoft Intuneと[Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)を使用してグループを追加し、コンプライアンス ポリシーを作成します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、グローバル管理者アカウントを使用してMicrosoft 365テスト ラボ サブスクリプションにサインインし、<a href="https://go.microsoft.com/fwlink/?linkid=2109431" target="_blank">エンドポイント マネージャー管理センター</a>を選択します。

    **[まだデバイス管理を有効にしていない**] のようなメッセージがまだ表示されている場合は、MDM 機関として [Intune] を選択します。 具体的な手順については、「 [モバイル デバイス管理機関の設定](/mem/intune/fundamentals/mdm-authority-set)」を参照してください。

    エンドポイント マネージャー管理センターは、デバイス管理とアプリ管理に重点を置きます。 この管理センターのツアーについては、「[チュートリアル: チュートリアル Intune in Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)」を参照してください。

2. **グループ** で、**割り当てられた** メンバーシップの種類 **を** 持つ **、マネージド Windows 10 デバイス ユーザー** という名前の新しいMicrosoft 365または **セキュリティ** グループを追加します。 次の手順では、コンプライアンス ポリシーをこのグループに割り当てます。 

    具体的な手順と、**Microsoft 365** または **セキュリティ** グループの詳細については、「[ユーザーとデバイスを整理するグループの追加](/mem/intune/fundamentals/groups-add)」を参照してください。

3. **デバイス** で、Windows 10コンプライアンス ポリシーを作成します。 作成した **マネージド Windows 10 デバイス ユーザー** グループにこのポリシーを割り当てます。

    ポリシーでは、単純なパスワードをブロックしたり、ファイアウォールを必要としたり、Microsoft Defender マルウェア対策サービスを実行する必要があります。 コンプライアンス ポリシーには、通常、基本設定、またはすべてのデバイスに必要な最小限の設定が含まれます。

    特定の手順と、構成できるコンプライアンス設定の詳細については、「 [コンプライアンス ポリシーを使用して管理するデバイスのルールを設定する](/mem/intune/protect/device-compliance-get-started)」を参照してください。

完了すると、**Managed Windows 10 デバイス ユーザー** グループのメンバーをテストするためのデバイス コンプライアンス ポリシーが作成されます。
  
## <a name="next-step"></a>次の手順

テスト環境で [追加のモバイル デバイス管理機能](m365-enterprise-test-lab-guides.md#mobile-device-management) と機能を確認します。

## <a name="see-also"></a>関連項目

[エンタープライズ テスト ラボ ガイドのMicrosoft 365](m365-enterprise-test-lab-guides.md)。
  
[エンタープライズ テスト環境のMicrosoft 365に iOS デバイスと Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
