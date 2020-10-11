---
title: 電子メールメッセージを暗号化するためのメールフロールールを定義する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 メッセージ暗号化を使用してメッセージを暗号化および復号化するメールフロールール (トランスポートルール) を作成する方法を学習できます。
ms.openlocfilehash: 28486f601a79e294550bbceb48ad57069024fd5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408607"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>電子メールメッセージを暗号化するためのメールフロールールを定義する

全体管理者は、送受信する電子メールメッセージを保護するためのメールフロールール (トランスポートルールとも呼ばれます) を作成できます。 送信電子メールメッセージを暗号化したり、組織内から送信される暗号化されたメッセージから暗号化を削除したり、組織から送信された暗号化メッセージへの返信を削除したりするためのルールを設定できます。 これらのルールを作成するには、Exchange 管理センター (EAC) または Exchange Online PowerShell を使用できます。 全体的な暗号化ルールのほかに、エンド ユーザー向けの個別メッセージ暗号化のオプションの有効/無効を選択できます。

組織外の送信者からの受信メールを暗号化することはできません。

Active Directory RMS から Azure Information Protection に最近移行した場合は、既存のメールフロールールを確認して、新しい環境で引き続き使用できることを確認する必要があります。 また、Azure Information Protection を使用して利用できる新しい Office 365 Message Encryption (OME) 機能を利用する場合は、既存のメールフロールールを更新する必要があります。 そうしないと、ユーザーは、新しいシームレスな OME の操作ではなく、前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。 まだ OME をセットアップしていない場合は、「 [Office の新しい365メッセージ暗号化機能を設定](set-up-new-message-encryption-capabilities.md) する」を参照してください。

メールフロールールを構成するコンポーネントと、メールフロールールのしくみについては、「 [Exchange Online のメールフロールール (トランスポートルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。 メールフロールールが Azure Information Protection でどのように機能するかの詳細については、「 [Azure Information protection のラベルの Exchange Online メールフロールールの構成](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)」を参照してください。

> [!IMPORTANT]
> ハイブリッド Exchange 環境では、オンプレミスのユーザーは、電子メールが Exchange Online を経由してルーティングされている場合にのみ、OME を使用して暗号化されたメールを送受信できます。 ハイブリッド Exchange 環境で OME を構成するには、まずハイブリッド [構成ウィザードを使用してハイブリッドを構成](https://docs.microsoft.com/Exchange/exchange-hybrid) し、次に、 [office 365 から電子メールサーバーにメールが流れる](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) ように構成し、 [電子メールサーバーから office 365 にメールが流れるよう](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)に構成する必要があります。 Office 365 を通過するようにメールを構成したら、このガイダンスを使用して OME のメールフロールールを構成できます。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>メールフロールールを作成して、新しい OME 機能で電子メールメッセージを暗号化する

EAC を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義できます。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能で電子メールメッセージを暗号化するためのルールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [ **管理** ] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、[**メールフロー** ] [ルール] に移動し、 \> **Rules** [新しい**New** ![ 新規作成] アイコンを選択して ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [ **名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。

6. [ **次の場合、このルールを適用**する] で条件を選択し、必要に応じて値を入力します。 たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[ **名前の確認** ] ボックスに電子メールアドレスを入力し、[ **名前の確認** \> **]** を選択します。

7. 他の条件を追加するには、[ **その他のオプション** ] を選択し、[ **条件の追加** ] を選択して、一覧から選択します。

   たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部**の \> **組織外**にある] を選択し \> **OK**ます。

8. 新しい OME 機能を使用して暗号化を有効にするには、 **次の操作を行い**ます。次に、[ **メッセージのセキュリティを変更** する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[ **保存**] を選択して、[ **OK]** を選択します。
  
  テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「office の [365 新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、Office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [ **転送** しない] オプションの詳細については、「 [メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [ **暗号化のみ** ] オプションの詳細については、「 [電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

  別のアクションを指定する場合は、[ **アクションの追加** ] を選択できます。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>EAC を使用して既存のメールフロールールを更新し、新しい OME 機能を使用する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [ **管理** ] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

5. メールフロールールの一覧で、新しい OME 機能を使用するように変更するルールを選択し、[編集] [編集] アイコン **を選択し** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。

6. 新しい OME 機能を使用して暗号化を有効にするには、 **次の操作を行い**ます。次に、[ **メッセージのセキュリティを変更** する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[ **保存** ] を選択して、[ **OK]** を選択します。

   テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「 [Azure Information Protection の上に構築された新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」に記載されているように、新しい機能を使用して Office 365 メッセージの暗号化を設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [ **転送** しない] オプションの詳細については、「 [メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [ **暗号化のみ** ] オプションの詳細については、「 [電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

   別のアクションを指定する場合は、[ **アクションの追加** ] を選択できます。

7. [ **実行** する処理] で、 **メッセージセキュリティを変更**するために割り当てられているアクションを削除し \> ます。 **以前のバージョンの OME を適用**します。

8. **[保存]** を選択します。

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>新しい OME 機能を使用して送信電子メールメッセージの暗号化を削除するメールフロールールを作成する

EAC を使用して、新しい OME 機能を使用したメッセージ暗号化の削除をトリガーするためのメールフロールールを定義できます。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能で電子メールメッセージから暗号化を削除するルールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [ **管理** ] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、[**メールフロー** ] [ルール] に移動し、 \> **Rules** [新しい**New** ![ 新規作成] アイコンを選択して ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [ **名前**] に、[送信メールからの暗号化を削除する] など、ルールの名前を入力します。

6. [ **このルールを適用**する条件] で、メッセージから暗号化を削除する条件を選択します。 **[送信者**を追加する] は、 \> **組織内**に配置します。 ここで、 **受信者が** \> **組織の外部**にあるなど、特定の受信者に対して追加条件を追加します。

7. [ **実行する処理**] で、[ **メッセージのセキュリティを変更する**] [ \> **Office 365 のメッセージの暗号化と権限の保護を削除**する] を選択します。

8. **[保存]** を選択します。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>新しい機能を使用せずに Office 365 メッセージ暗号化のメールフロールールを作成する

まだ組織を新しい OME 機能に移行していない場合は、組織にとって適切であるとすぐに、新しい OME 機能に移行するための計画を行うことをお勧めします。 手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 それ以外の場合は、「 [Office 365 のメールフロールールを定義する」の「新しい OME 機能を使用しない](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)」を参照してください。

## <a name="related-topics"></a>関連項目

[Office 365 での暗号化](encryption.md)

[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)

[暗号化メッセージへのブランドの追加](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
