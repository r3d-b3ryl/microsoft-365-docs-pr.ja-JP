---
title: メール メッセージを暗号化するためのメール フロー ルールを定義
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: 管理者は、Microsoft Purview Message Encryptionを使用してメッセージを暗号化および暗号化解除するためのメール フロー ルール (トランスポート ルール) を作成する方法について学習できます。
ms.openlocfilehash: 75abd302bf661fda50b144f431572c8c6dfc8bcc
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635701"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>メール メッセージを暗号化するためのメール フロー ルールを定義

Exchange Onlineを管理する管理者は、送受信するメール メッセージを保護するために、メール フロー ルール (トランスポート ルールとも呼ばれます) を作成できます。 送信電子メール メッセージを暗号化し、組織内から送信された暗号化されたメッセージまたは組織内から送信された暗号化されたメッセージへの返信から暗号化を削除するルールを設定できます。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター (EAC)</a> または powerShell Exchange Onlineを使用して、これらのルールを作成できます。 全体的な暗号化ルールのほかに、エンド ユーザー向けの個別メッセージ暗号化のオプションの有効/無効を選択できます。

組織外の送信者からの受信メールを暗号化することはできません。

Active Directory RMS から Azure Information Protectionに最近移行した場合は、既存のメール フロー ルールを確認して、新しい環境で引き続き動作することを確認する必要があります。 また、Azure Information ProtectionでMicrosoft Purview Message Encryptionを使用するには、既存のメール フロー ルールを更新する必要があります。 そうしないと、ユーザーは、新しいシームレスなエクスペリエンスではなく、以前の HTML 添付ファイル形式を使用する暗号化されたメールを引き続き受信します。 メッセージの暗号化をまだ設定していない場合は、「Microsoft Purview Message Encryptionの[設定](set-up-new-message-encryption-capabilities.md)」を参照してください。

メール フロー ルールを構成するコンポーネントとメール フロー ルールのしくみについては、[Exchange Onlineのメール フロー ルール (トランスポート ルール) を](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)参照してください。 Azure Information Protectionでのメール フロー ルールの動作の詳細については、「Azure [Information Protection ラベルのメール フロー ルールExchange Online構成する」を](/azure/information-protection/deploy-use/configure-exo-rules)参照してください。

> [!IMPORTANT]
> ハイブリッド Exchange 環境の場合、オンプレミスユーザーは、電子メールがExchange Online経由でルーティングされている場合にのみ、メッセージ暗号化を使用して暗号化されたメールを送受信できます。 ハイブリッド Exchange 環境でメッセージの暗号化を構成するには、最初に[ハイブリッド構成ウィザードを使用してハイブリッドを構成](/Exchange/exchange-hybrid)し、[次にメールをOffice 365から電子メール サーバーにフローするように構成](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)し、[メール サーバーからOffice 365にフローするようにメールを構成する必要があります](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 Office 365を経由するようにメールを構成したら、このガイダンスを使用してメッセージ暗号化のメール フロー ルールを構成できます。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionを使用して電子メール メッセージを暗号化するメール フロー ルールを作成する

EAC を使用してメッセージ暗号化をトリガーするためのメール フロー ルールを定義できます。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-microsoft-purview-message-encryption"></a>EAC を使用して、Microsoft Purview Message Encryptionを使用して電子メール メッセージを暗号化するためのルールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用して、[Office 365にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. **管理** タイルを選択します。

3. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で、[**管理 センター** \> **Exchange**] を選択します。

4. EAC の [**メール フロー** \> **ルール**] に移動し、[**新しい新規**![] アイコンを選択します。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**新しいルールを作成します**。 EAC の使用の詳細については、[Exchange Onlineの Exchange 管理センターに関するページを](/exchange/exchange-admin-center)参照してください。

5. **[名前]** に、ルールの名前 ([DrToniRamos@hotmail.com のメールを暗号化する] など) を入力します。

6. [ **このルールを適用する場合**] で条件を選択し、必要に応じて値を入力します。 たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[**チェック名**] ボックスに電子メール アドレスを入力し、[OK] チェック **ボックス**\>をオン **にします**。

7. さらに条件を追加するには、[ **その他のオプション** ] を選択し、[ **条件の追加** ] を選択して一覧から選択します。

   たとえば、受信者が組織外の場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者は組織** の **外部**\>/内部\>] **を選択します。**

8. メッセージ暗号化を有効にするには、[**次の操作]** から [**メッセージ セキュリティの変更**] を選択し、[メッセージ **の暗号化と権限の保護Office 365適用**] を選択します。 一覧から RMS テンプレートを選択し、[ **保存]** を選択して、[ **OK] を選択します**。
  
  テンプレートの一覧には、既定のすべてのテンプレートとオプション、およびOffice 365で使用するために作成したカスタム テンプレートが含まれます。 リストが空の場合は、「Microsoft Purview Message Encryptionのセットアップ」の説明に従って[Microsoft Purview Message Encryptionを設定](set-up-new-message-encryption-capabilities.md)していることを確認します。 既定のテンプレートの詳細については、「[Azure Information Protection 用のテンプレートの構成と管理](/information-protection/deploy-use/configure-policy-templates)」を参照してください。 [ **転送しない** ] オプションの詳細については、「 [電子メールの転送不可オプション」を](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)参照してください。 **暗号化専用** オプションの詳細については、[電子メールの暗号化専用オプションに関するページを](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)参照してください。

  別のアクションを指定する場合は、 **アクションの追加** を選択できます。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-microsoft-purview-message-encryption"></a>EAC を使用して、Microsoft Purview Message Encryptionを使用するように既存のメール フロー ルールを更新する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用して、[Office 365にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. **管理** タイルを選択します。

3. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で、[**管理 センター** \> **Exchange**] を選択します。

4. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

5. メール フロー ルールの一覧で、Microsoft Purview Message Encryptionで使用する変更するルールを選択し、[**編集]** ![アイコンを選択します](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。

6. Microsoft Purview Message Encryptionを使用して暗号化を有効にするには、[**次の操作]** から [**メッセージ セキュリティの変更**] を選択し、[メッセージ **の暗号化と権限の保護Office 365適用**] を選択します。 一覧から RMS テンプレートを選択し、[ **保存]** を選択してから [ **OK] を選択します**。

   テンプレートの一覧には、既定のすべてのテンプレートとオプション、およびOffice 365で使用するために作成したカスタム テンプレートが含まれます。 リストが空の場合は、「Microsoft Purview Message Encryptionのセットアップ」の説明に従って[Microsoft Purview Message Encryptionを設定](set-up-new-message-encryption-capabilities.md)していることを確認します。 既定のテンプレートの詳細については、「[Azure Information Protection 用のテンプレートの構成と管理](/information-protection/deploy-use/configure-policy-templates)」を参照してください。 [転送しない] オプションの詳細については、「 [電子メールの転送不可オプション」を](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)参照してください。 暗号化専用オプションの詳細については、「 [電子メールの暗号化のみオプション」を](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)参照してください。

   別のアクションを指定する場合は、 **アクションの追加** を選択できます。

7. **次の操作の** 一覧から、**メッセージ セキュリティ**\>の変更に割り当てられているすべてのアクションを削除します。**以前のバージョンの OME を適用** します。

8. **[保存]** を選択します。

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionを使用して電子メール メッセージの暗号化を削除するメール フロー ルールを作成する

EAC を使用して、Microsoft Purview Message Encryptionを使用してメッセージ暗号化を削除するメール フロー ルールを定義できます。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-microsoft-purview-message-encryption"></a>EAC を使用して、Microsoft Purview Message Encryptionを使用して電子メール メッセージから暗号化を削除するルールを作成する

組織によって適用されたメッセージから暗号化を削除できます。 暗号化された添付ファイルから暗号化を削除して、電子メール メッセージ全体が保護されないようにすることもできます。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用して、[Office 365にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. **管理** タイルを選択します。

3. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で、[**管理 センター** \> **Exchange**] を選択します。

4. EAC の [**メール フロー** \> **ルール**] に移動し、[**新しい新規**![] アイコンを選択します。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**新しいルールを作成します**。 EAC の使用の詳細については、[Exchange Onlineの Exchange 管理センターに関するページを](/exchange/exchange-admin-center)参照してください。

5. **[名前]** に、ルールの名前を入力します (例: `Remove encryption from outgoing mail`.

6. [ **このルールを適用する場合**] で、メッセージから暗号化を削除する条件を選択します。 [追加 **] 送信者は、**\>メールを送信するための **組織内**_にあるか_**、受信者が** メールを受信するための **組織内** にあります\>。

7. [**次の操作を行う**] で、[**メッセージ セキュリティ**\>の変更 **] Office 365 [メッセージの暗号化と権限保護の適用] を選択** します。

8. (省略可能)[**次の操作を行う**] で、[**メッセージ セキュリティ**\>の変更] を選択し、**組織によって適用される添付ファイルの権利保護を削除します**。

ルールを保存します。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionを使用せずにメッセージ暗号化Office 365メール フロー ルールを作成する

まだ組織をMicrosoft Purview Message Encryptionに移行していない場合は、組織にとって妥当な場合は、すぐに移行する計画を立てるようお勧めします。 手順については、「[Microsoft Purview Message Encryptionのセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 それ以外の場合は、「[Microsoft Purview Message Encryptionを使用しないメッセージ暗号化Office 365メール フロー ルールを定義する」を](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-microsoft-purview-message-encryption)参照してください。

## <a name="related-content"></a>関連コンテンツ

[Office 365 での暗号化](encryption.md)

[Microsoft Purview のメッセージの暗号化を設定する](set-up-new-message-encryption-capabilities.md)

[暗号化メッセージへのブランドの追加](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
