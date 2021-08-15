---
title: エンタープライズ テスト環境Microsoft 365デバイス コンプライアンス ポリシー
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
description: このテスト ラボ ガイドを使用して、Intune デバイス コンプライアンス ポリシーをエンタープライズ テスト環境Microsoft 365に追加します。
ms.openlocfilehash: 697837a93b92006f51aca5d20a5ad62bf130f1bbfaf2c4d00caddfe8ea7d12e1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53858905"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境Microsoft 365デバイス コンプライアンス ポリシー

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

この記事では、エンタープライズ テスト環境用に、デバイスとデバイスの Intune Windows 10ポリシー Microsoft 365 Apps for enterpriseをMicrosoft 365する方法について説明します。

Intune デバイスコンプライアンス ポリシーを追加するには、次の 2 つのフェーズが必要です。
- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: デバイスコンプライアンス ポリシーを作成して、Windows 10する](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件で軽量な方法でのみ MAM ポリシーを構成する場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> ライセンスとグループ の自動メンバーシップをテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: デバイスコンプライアンス ポリシーを作成して、Windows 10する

このフェーズでは、デバイスのコンプライアンス ポリシーを作成し、Windows 10します。 このフェーズでは、Microsoft Intune管理センター Microsoft エンドポイント マネージャー[を使用](https://go.microsoft.com/fwlink/?linkid=2109431)してグループを追加し、コンプライアンス ポリシーを作成します。

1. [管理者] [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、グローバル管理者アカウントMicrosoft 365テスト ラボ サブスクリプションにサインインします。 管理センター **エンドポイント マネージャー** 選択します。 管理[エンドポイント マネージャーが開](https://go.microsoft.com/fwlink/?linkid=2109431)きます。

    [デバイス管理を有効にしていない] に似たメッセージがまだ表示 **されている** 場合は、MDM 機関として [Intune] を選択します。 具体的な手順については、「モバイル デバイス管理 [機関の設定」を参照してください](/mem/intune/fundamentals/mdm-authority-set)。

    管理エンドポイント マネージャーは、デバイス管理とアプリ管理に重点を当て、 この管理センターのツアーについては、「チュートリアル: チュートリアル Intune in Microsoft エンドポイント マネージャー」[を参照してください](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。

2. [**グループ]** で、[割り当てられたMicrosoft 365の種類を持つ **、Managed** Windows 10という名前の新しいグループまたはセキュリティ グループ **を** 追加します。 次の手順では、コンプライアンス ポリシーをこのグループに割り当てします。 

    特定の手順、およびセキュリティ グループまたはセキュリティ **Microsoft 365については**、「グループを追加してユーザー **とデバイスを** 整理する [」を参照してください](/mem/intune/fundamentals/groups-add)。

3. [**デバイス]** で、コンプライアンス ポリシー Windows 10作成します。 作成したデバイス ユーザー グループの **管理Windows 10に** このポリシーを割り当てる。

    ポリシーでは、単純なパスワードをブロックし、ファイアウォールを要求し、Microsoft Defender Antimalware サービスを実行する必要があります。 コンプライアンス ポリシーには、通常、すべてのデバイスに必要な基本設定または最低限の設定が含まれます。

    具体的な手順、および構成できるコンプライアンス設定の詳細については、「コンプライアンス ポリシーを使用して管理するデバイスのルールを設定する」 [を参照してください](/mem/intune/protect/device-compliance-get-started)。

完了すると、Managed Windows 10デバイス ユーザー グループのメンバー **をテストするデバイス コンプライアンス ポリシーがあります**。
  
## <a name="next-step"></a>次の手順

テスト環境 [で、その他の](m365-enterprise-test-lab-guides.md#mobile-device-management) モバイル デバイス管理機能を確認します。

## <a name="see-also"></a>関連項目

[Microsoft 365テスト ラボ ガイドの詳細](m365-enterprise-test-lab-guides.md)
  
[エンタープライズ テスト環境用に iOS Microsoft 365 Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
