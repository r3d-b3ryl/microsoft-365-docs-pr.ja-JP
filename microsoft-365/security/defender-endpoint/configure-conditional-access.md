---
title: Microsoft Defender for Endpointで条件付きアクセスを構成する
description: 条件付きアクセスを実装するためにIntune、Microsoft 365 Defender、Azure で行う必要がある手順について説明します
keywords: 条件付きアクセス, 条件付き, アクセス, デバイス リスク, リスク レベル, 統合, Intune 統合
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8706f756b4e8d0ba87a747396e8f7ef71d66460c
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284375"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointで条件付きアクセスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。

## <a name="before-you-begin"></a>開始する前に

> [!WARNING]
> このシナリオでは、登録済みデバイスAzure ADサポートされていないことに注意してください。</br>
> Intune登録済みデバイスのみがサポートされます。

すべてのデバイスがIntuneに登録されていることを確認する必要があります。 次のいずれかのオプションを使用して、デバイスをIntuneに登録できます。

- IT 管理者: 自動登録を有効にする方法の詳細については、「[Windows登録](/intune/windows-enroll#enable-windows-10-automatic-enrollment)」を参照してください。
- エンド ユーザー: IntuneにWindows 10デバイスとWindows 11 デバイスを登録する方法の詳細については、「Windows 10 [デバイスをIntuneに登録](/intune/quickstart-enroll-windows-device)する」を参照してください。
- エンド ユーザーの代替手段: Azure AD ドメインへの参加の詳細については、「[方法: Azure AD参加の実装を計画する](/azure/active-directory/devices/azureadjoin-plan)」を参照してください。

Microsoft 365 Defender、Intune ポータル、Azure AD ポータルで実行する必要がある手順があります。

これらのポータルにアクセスし、条件付きアクセスを実装するために必要なロールに注意することが重要です。

- **Microsoft 365 Defender** - 統合を有効にするには、グローバル管理者ロールを使用してポータルにサインインする必要があります。
- **Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。
- **Azure AD ポータル** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。

> [!NOTE]
> Microsoft Intune環境が必要です。IntuneマネージドデバイスとAzure AD Windows 10デバイスとWindows 11デバイスに参加しています。

条件付きアクセスを有効にするには、次の手順に従います。

- 手順 1: Microsoft 365 DefenderからMicrosoft Intune接続を有効にする
- 手順 2: Intuneで Defender for Endpoint 統合を有効にする
- 手順 3: Intuneでコンプライアンス ポリシーを作成する
- 手順 4: ポリシーを割り当てる 
- 手順 5: Azure AD条件付きアクセス ポリシーを作成する

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>手順 1: Microsoft Intune接続を有効にする

1. ナビゲーション ウィンドウで、[**Endpoints** \> **General** \> **Advanced features** \> Microsoft Intune **connection**] **設定**\>選択します。
2. Microsoft Intune設定を **[オン]** に切り替えます。
3. [ **保存] 環境設定をクリックします**。

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>手順 2: Intuneで Defender for Endpoint 統合を有効にする

1. [Azure portal](https://portal.azure.com)にサインインします。
2. [ **デバイス コンプライアンス** \> **] Microsoft Defender ATP** を選択します。
3. **Connect Windows 10.0.15063 以降のデバイスを Microsoft Defender Advanced Threat Protection を** **[オン]** に設定します。
4. [**保存**] をクリックします。

### <a name="step-3-create-the-compliance-policy-in-intune"></a>手順 3: Intuneでコンプライアンス ポリシーを作成する

1. [Azure portal](https://portal.azure.com)で、[**すべてのサービス**] を選択し、**Intune** でフィルター処理して **、[Microsoft Intune**] を選択します。
2. [ **デバイス コンプライアンス** \> **ポリシーの** \> **作成ポリシー**] を選択します。
3. 名前と **説明** を入力 **します**。
4. **プラットフォーム** で、**Windows 10以降を** 選択します。
5. **[デバイスの正常性**] 設定 **で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを** 好みのレベルに設定します。

   - **[セキュリティ保護]**: このレベルはセキュリティ上最も安全です。 デバイスに既存の脅威を持つことはできません。それでも会社のリソースにアクセスできます。 いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。
   - **[低]**: 低レベルの脅威が存在する場合にのみ、デバイスは準拠しています。 脅威レベルが中程度または高いデバイスは準拠していません。
   - **[中]**: デバイスに存在する脅威が低または中の場合、デバイスは準拠しています。 高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。
   - **高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。 そのため、脅威レベルが高い、中、低のデバイスは準拠していると見なされます。

6. **[OK] を** 選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。

### <a name="step-4-assign-the-policy"></a>手順 4: ポリシーを割り当てる

1. [Azure portal](https://portal.azure.com)で、[**すべてのサービス**] を選択し、**Intune** でフィルター処理して **、[Microsoft Intune**] を選択します。
2. [**デバイス コンプライアンス** \> **ポリシー**] を選択>、Microsoft Defender for Endpointコンプライアンス ポリシーを選択します。
3. **[割り当て]** を選択します。
4. ポリシーを割り当てるには、Azure AD グループを含めるか除外します。
5. ポリシーをグループに展開するには、[保存] を選択 **します**。 ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>手順 5: Azure AD条件付きアクセス ポリシーを作成する

1. [Azure portal](https://portal.azure.com)で、**条件付きアクセス** \> **の新しいポリシー** **Azure Active Directory**\>開きます。
2. ポリシー **名** を入力し、[ **ユーザーとグループ**] を選択します。 含めるオプションまたは除外するオプションを使用して、ポリシーのグループを追加し、**[完了]** を選択します。
3. **クラウド アプリ** を選択し、保護するアプリを選択します。 たとえば、**[アプリを選択]** を選び、**[Office 365 SharePoint Online]** と **[Office 365 Exchange Online]** を選択します。 [**完了**] を選んで変更内容を保存します。

4. **[条件** \> **クライアント アプリ**] を選択して、アプリとブラウザーにポリシーを適用します。 たとえば、**[はい]** を選択し、**[ブラウザー]** と **[モバイル アプリとデスクトップ クライアント]** を有効にします。 [**完了**] を選んで変更内容を保存します。

5. **[許可]** を選択し、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。 たとえば、[アクセス\>**を許可****するデバイスを準拠としてマークする]** を選択します。 **[選択]** を選んで変更を保存します。

6. **[ポリシーを有効にする]**、**[作成]** の順に選択して変更を保存します。

詳細については、「[Intune で条件付きアクセスによる Microsoft Defender for Endpoint のコンプライアンスを強制する](/intune/advanced-threat-protection)」を参照してください。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
