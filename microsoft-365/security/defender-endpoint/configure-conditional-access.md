---
title: Microsoft Defender for Endpoint で条件付きアクセスを構成する
description: 条件付きアクセスを実装するために Intune、Microsoft 365 Defender、Azure で実行する必要がある手順について説明します。
keywords: 条件付きアクセス、条件付きアクセス、デバイス リスク、リスク レベル、統合、Intune 統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2460b1aac746e706175524e7f201610a1888c255
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655865"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で条件付きアクセスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。

## <a name="before-you-begin"></a>はじめに

> [!WARNING]
> このシナリオでは、登録されているデバイスAD Azure がサポートされていない点に注意することが重要です。</br>
> Intune に登録されているデバイスだけがサポートされています。

すべてのデバイスが Intune に登録されている必要があります。 Intune にデバイスを登録するには、次のオプションを使用できます。

- IT 管理者: 自動登録を有効にする方法の詳細については、「登録」[を参照Windowsしてください。](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- エンド ユーザー: Intune にデバイスを登録する方法の詳細Windows 10 Intune にデバイスを登録するWindows 10[を参照してください。](/intune/quickstart-enroll-windows-device)
- エンド ユーザーの代替: Azure AD ドメインへの参加の詳細については、「How [to: Plan your Azure AD参加実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。

Intune ポータル、Intune ポータル、および Azure Microsoft 365 Defenderポータルで実行するADがあります。

これらのポータルにアクセスし、条件付きアクセスを実装するために必要な役割に注意することが重要です。

- **Microsoft 365 Defender** - 統合を有効にするには、グローバル管理者の役割を持つポータルにサインインする必要があります。
- **Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。
- **Azure ADポータル** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。

> [!NOTE]
> Intune が管理され、Azure Microsoft Intuneがデバイスに参加しているAD環境Windows 10があります。

条件付きアクセスを有効にするには、次の手順を実行します。

- 手順 1: デバイスから接続Microsoft IntuneオンMicrosoft 365 Defender
- 手順 2: Intune で Defender for Endpoint 統合を有効にする
- 手順 3: Intune でコンプライアンス ポリシーを作成する
- 手順 4: ポリシーを割り当てる 
- 手順 5: 条件付きアクセス ポリシー AD Azure を作成する

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>手順 1: 接続を有効Microsoft Intuneする

1. ナビゲーション ウィンドウで、[エンドポイントの全般高度な **設定** 接続  >    >    >  **] を選択Microsoft Intune**  >  **します**。
2. [設定] Microsoft Intuneを [オン] に **切り替える**。
3. [設定 **の保存] をクリックします**。

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>手順 2: Intune で Defender for Endpoint 統合を有効にする

1. [Azure portal](https://portal.azure.com) にサインインします。
2. [デバイス **コンプライアンス**  >  **] [Microsoft Defender ATP] を選択します**。
3. Microsoft Defender advanced threat protection **Connect Windows 10.0.15063+** デバイスを On に設定 **します**。
4. **[保存]** をクリックします。

### <a name="step-3-create-the-compliance-policy-in-intune"></a>手順 3: Intune でコンプライアンス ポリシーを作成する

1. Azure portal [で、[すべてのサービス](https://portal.azure.com)**]** を選択し **、Intune** でフィルター処理し、[**すべてのサービス]** を選択Microsoft Intune。
2. [デバイス **コンプライアンス ポリシー**  >  **] [ポリシー**  >  **の作成] を選択します**。
3. [名前] **と [説明** ] を **入力します**。
4. [**プラットフォーム] で****、[Windows 10] を選択します**。
5. [デバイス **の正常性] 設定** で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを希望する **レベルに設定** します。

   - **セキュリティ** 保護 : このレベルが最も安全です。 デバイスは、既存の脅威を持ち、会社のリソースに引き続きアクセスすることはできません。 脅威が見つかった場合、デバイスは非準拠として評価されます。
   - **低**: 低レベルの脅威だけが存在する場合、デバイスは準拠しています。 中程度または高い脅威レベルを持つデバイスは、準拠していません。
   - **中**: デバイスで検出された脅威が低または中程度の場合、デバイスは準拠しています。 高レベルの脅威が検出された場合、デバイスは非準拠と判断されます。
   - **高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。 そのため、高、中、低の脅威レベルを持つデバイスは、準拠しているとみなされます。

6. **[OK]** を選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。

### <a name="step-4-assign-the-policy"></a>手順 4: ポリシーを割り当てる

1. Azure portal [で、[すべてのサービス](https://portal.azure.com)**]** を選択し **、Intune** でフィルター処理し、[**すべてのサービス]** を選択Microsoft Intune。
2. [**デバイス コンプライアンス ポリシー**  >  **] を選択>** Microsoft Defender for Endpoint コンプライアンス ポリシーを選択します。
3. **[割り当て]** を選択します。
4. ポリシーを割り当てるには、Azure ADグループを含めるか除外します。
5. ポリシーをグループに展開するには、[保存] を **選択します**。 ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>手順 5: 条件付きアクセス ポリシー AD Azure を作成する

1. Azure portal [で、[条件付きアクセス](https://portal.azure.com)**] Azure Active Directory**  >  **ポリシーを**  >  **開きます**。
2. ポリシー名を入力 **し、[** ユーザーとグループ **] を選択します**。 [含める] または [除外] オプションを使用してポリシーのグループを追加し、[完了] を **選択します**。
3. [ **クラウド アプリ] を** 選択し、保護するアプリを選択します。 たとえば、[アプリの選択 **] を** 選択し、[オンライン] と **[Office 365 SharePoint]** **を** Office 365 Exchange Online。 [**完了**] を選んで変更内容を保存します。

4. [**条件**  >  **クライアント アプリ] を** 選択して、アプリとブラウザーにポリシーを適用します。 たとえば、[はい] **を選択** し、[ **ブラウザー** とモバイル アプリと **デスクトップ クライアント] を有効にします**。 [**完了**] を選んで変更内容を保存します。

5. [許可 **] を** 選択して、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。 たとえば、[アクセスを許可 **するデバイス**  >  **に準拠としてマークする] を選択します**。 [選択 **] を** 選択して変更を保存します。

6. [ポリシー **を有効にする]** を選択し、[ **作成] を選択して** 変更を保存します。

詳細については、「Intune での条件付きアクセスを使用した Microsoft Defender for Endpoint のコンプライアンスの [適用」を参照してください](/intune/advanced-threat-protection)。

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
