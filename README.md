# color-label


   {% if product.options[forloop.index0] == 'Color' %}
                        <div class="custom-color">
                      <fieldset class="js product-form__input {{ option.name }}">
                        <legend class="form__label">{{ option.name }}</legend>
                        {%- for value in option.values -%}
                          <input
                            type="radio"
                            id="{{ section.id }}-{{ option.position }}-{{ forloop.index0 }}"
                            name="{{ option.name }}"
                            value="{{ value | escape }}"
                            form="{{ product_form_id }}"
                            {% if option.selected_value == value %}
                              checked
                            {% endif %}
                          >
                          <label for="{{ section.id }}-{{ option.position }}-{{ forloop.index0 }}" style="background-color: {{ value | split: ' ' | last | handle }} !important; background-image: url({{ value | handle | append: '.png' | asset_url }})">
                             <div class="tooltip">
                          <span class="tooltiptext">{{ value }}</span>
                          </div>
                          </label>
                       
                        {%- endfor -%}
                      </fieldset>
                        </div>
