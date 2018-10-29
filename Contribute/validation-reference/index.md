---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084424"
---
# <a name="docs-pr-validation-service"></a>Serviço de validação Docs PR

O serviço de validação Docs PR é um aplicativo do GitHub que executa regras de validação em arquivos em um PR.

Quando o serviço de validação estiver habilitado em um repositório, o seguinte comportamento ocorrerá:

1. Você envia um PR.
1. No comentário do GitHub que indica o status do PR, você verá o status de "verificações" habilitado no repositório. Neste exemplo, há duas verificações habilitadas, "Confirmar Validação" e "OpenPublishing.Build":

   ![algumas verificações falharam](media/validation-failed.png)

   O build poderá passar mesmo se a confirmação da validação falhar.

1. Clique em **Detalhes** para saber mais.
1. Na página Detalhes, você verá todas as verificações de validação que falharam, com informações sobre como corrigir os problemas:

   ![mensagem de validação](media/validation-details.png)

Confira o sumário à esquerda deste artigo para ver a lista de validações do serviço no momento.